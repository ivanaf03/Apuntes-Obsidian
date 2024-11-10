[[Tema 3-Promela y SPIN]]

## Macros
En Promela no existen las funciones. En su lugar se definen macros. Por ejemplo:

```c
// Single line macro
#define printnum(n) printf("%d\n", n)

// Multiple line macro
#define printnums(a, b) {
    int i = a;
    do
	    :: i <= b -> printnum(i); i++
	    :: i > b  -> break;
    od
}

init {
    printnums(1, 10)
}
```

## Procesos
Se pueden definir procesos que se ejecuten de forma concurrente. Se declaran con `active proctype [nombre proceso] ([args])`. Cada proceso tiene asignado un PID al que se puede acceder con `_pid`.

Los procesos se intercalan entre sí en la ejecución. Por ejemplo, este código tiene 6 posibles ejecuciones:
+ p1, p2, q1, q2
+ p1, q1, p2, q2
+ q1, q2, p1, p2
+ q1, p1, q2, p2
+ p1, q1, q2, p2
+ q1, p1, p2, q2

```c
byte n = 0;

active proctype P() {
    n = 1;
    printf("Process P, n = %d\n", n);
}

active proctype Q() {
    n = 2;
    printf("Process Q, n = %d\n", n);
}
```

### Ejercicio 1: Tenemos dos procesos secuenciales P y Q, con m > 0 y n > 0 instrucciones, respectivamente. Cuántas ejecuciones intercaladas diferentes obtenemos?

$$ \binom{m+n}{m} = \frac{m! \cdot n!}{(m+n)!} $$

## Mutex
Podemos declarar un grupo de sentencias como atómicas. Esto quiere decir que se ejecutan siempre en el mismo bloque, sin que otros procesos interrumpan. Se hace con `atomic`, de forma idéntica a un mutex en otros lenguajes de programación.

```c
byte n = 0;

active proctype P() {
    atomic {
        n = 1;
        printf("Process P, n = %d\n", n);
    } // Siempre se ejecuta este bloque secuencialmente
}

active proctype Q() {
    n = 2;
    printf("Process Q, n = %d\n", n);
}
```

## Procesos intercalados y sección crítica
Los procesos pueden dar lugar a diferentes ejecuciones gracias al no determinismo. Por ejemplo:

```c
int n = 5;

active proctype P() {
    do
    :: n < 10 -> printf("%d\n", n); n++
    :: n == 5 -> n = 7
    :: n == 10 -> break
    od
}

active proctype Q() {
    if 
    :: n < 0 -> n = 0 
    fi
}

active proctype R() {
    (n == 5);
    printf("five\n");
}
```

Si n vale 5, se puede ejecutar primero R, luego Q, que no hará nada y luego P, por lo que n valdrá 7. Pero otro ejemplo de ejecución sería que primero se ejecutara P, por lo que n valdría 7 y luego Q y R no harían nada. Con otros valores de n tendríamos situaciones similares.

### Sección crítica
Cuando se intercalan procesos los recursos compartidos entre ellos pueden verse afectados. Por ejemplo:

```c
int counter = 0; // Variable compartida entre los procesos

active proctype P() {
    do
    :: // Sección no crítica
       printf("Non-critical section P\n");

       // Sección crítica: modificar la variable compartida
       printf("P: Incrementing counter (before): %d\n", counter);
       counter = counter + 2;
       printf("P: Incrementing counter (after): %d\n", counter);
    od
}

active proctype Q() {
    do
    :: // Sección no crítica
       printf("Non-critical section Q\n");

       // Sección crítica: modificar la variable compartida
       printf("Q: Incrementing counter (before): %d\n", counter);
       counter = counter * 3;
       printf("Q: Incrementing counter (after): %d\n", counter);
    od
}
```

Este código puede tener diferentes ejecuciones y dar diferentes resultados de la variables counter. La variable está dentro de la sección crítica en ambos procesos.

### Exclusión mutua
La exclusión mutua consiste en el aislamiento de los procesos para que no entren al mismo tiempo a la sección crítica. Por ejemplo:

```c
bool wantP = false;  // Indica si el proceso P quiere entrar en la sección crítica
bool wantQ = false;  // Indica si el proceso Q quiere entrar en la sección crítica
byte turn = 0;       // Indica de quién es el turno (0 para P, 1 para Q)

active proctype P() {
    do
    :: // Sección no crítica de P
       printf("Non-critical section P\n");

       // Proceso P quiere entrar en la sección crítica
       wantP = true;
       turn = 1;  // Cede el turno a Q

       // Espera hasta que Q termine su sección crítica o sea su turno
       do
       :: (wantQ && turn == 1) -> skip  // Espera mientras wantQ y turno para Q
       :: (!wantQ || turn == 0) -> break // Sale del bucle si no quiere o es su turno
       od;

       // Sección crítica de P
       printf("Critical section P\n");

       // Proceso P ha terminado su sección crítica
       wantP = false;
    od
}

active proctype Q() {
    do
    :: // Sección no crítica de Q
       printf("Non-critical section Q\n");

       // Proceso Q quiere entrar en la sección crítica
       wantQ = true;
       turn = 0;  // Cede el turno a P

       // Espera hasta que P termine su sección crítica o sea su turno
       do
       :: (wantP && turn == 0) -> skip  // Espera mientras wantP y turno para P
       :: (!wantP || turn == 1) -> break // Sale del bucle si no quiere o es su turno
       od;

       // Sección crítica de Q
       printf("Critical section Q\n");

       // Proceso Q ha terminado su sección crítica
       wantQ = false;
    od
}
```

Si se hace mal la exclusión mutua, todos los procesos se quedan esperando se produce un deadlock. SPIN responde produciendo un timeout. Se puede encontrar con `spin -search ejemplo.pml`.

Podemos comprobar que se satisface la exclusión mutua con `spin -a` y una fórmula de lógica temporal. Por ejemplo, en vez de aserciones se puede definir una condición `#define mutex (critical<2)`. Para comprobar que siempre se cumple la condición ejecutamos el código con `spin -a -f '![]mutex' ejemplo.pml`.

Otra forma es con el uso de etiquetas:

```c
bool wantP = false, wantQ = false;

active proctype P() {
    do
	:: printf("Non-critical section P\n");
		wantP = true;
       !wantQ;
	    cs: printf("Critical section P\n");
       wantP = false;
    od
}

active proctype Q() {
	do 
	:: printf("Non-critical section Q\n"); 
		wantQ=true;
		!wantP; 
		cs: printf("Critical section Q\n"); 
		wantQ=false; 
	od
```

Se puede comprobar que se llega a las etiquetas con `spin -a -f '!<>(P@cs && Q@cs)' ejemplo.pml`.

## Semáforos
Podemos declarar un semáforo mediante la sentencia `atomic` y el uso de macros:

```c
byte sem = 1;

inline wait(sem) {
    atomic {
        sem > 0;  
        sem--;   
    }
}

inline signal(sem) {
    sem++;  
}

active proctype P() {
    do
    :: // Sección no crítica de P
       printf("Non-critical section P\n");
       
       // Espera para entrar en la sección crítica
       wait(sem);

       // Sección crítica de P
       printf("Critical section P\n");
       
       // Termina su sección crítica
       signal(sem);
    od
}

active proctype Q() {
    do
    :: // Sección no crítica de Q
       printf("Non-critical section Q\n");
       
       // Espera para entrar en la sección crítica
       wait(sem);

       // Sección crítica de Q
       printf("Critical section Q\n");
       
       // Termina su sección crítica
       signal(sem);
    od
}
```

## Procesos múltiples
Podemos hacer que un mismo proceso tenga varias copias mediante la sentencia `active[N]`. Por ejemplo:

```c
active [3] proctype P() {
    do
    :: printf("Non-critical section P\n");
       wait(mutex);
       
       cs: printf("Critical section P\n");
       signal(mutex);
    od
}
```

La variable `_nr_pr` devuelve el número de procesos activos.

### Init
Para creación más compleja de procesos podemos usar `init` y llamarlos desde ahí con `run`. Por ejemplo:

```c
proctype P(byte c, int n) { 
	printf("Executing process %c (%d)\n", c, n); 
}

init { 
	printf("Starting...\n"); 
	run P('A', 0); 
	run P('B', 1);
	(_nr_pr == 0);
	printf("All process terminated\n") 
}
```








