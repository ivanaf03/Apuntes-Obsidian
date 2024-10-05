[[Tema 3-Promela y SPIN]]

## Qué es Promela?
Promela no es un lenguaje de programación, sino un lenguaje de modelado y especificación que permite describir el comportamiento de uno o varios procesos ejecutados concurrentemente.

### SPIN
SPIN es una herramienta que permite modelar y verificar los modelos escritos en Promela. Recibe como entradas un modelo y unas condiciones y hace un reporte de errores y muestra las trazas de ejecución.

### Ejemplos en Promela
Por ejemplo, podemos crear un programa que imprima "Hola mundo":

```c
init {
    printf("Hola mundo\n")
}
```

Otro ejemplo básico, un programa que invierte el número 123:

```c
init {
    int value = 123;
    int reversed;
    
    reversed = (value % 10) * 100 + ((value / 10) % 10) * 10 + (value / 100);

    printf("value=%d, reversed=%d\n", value, reversed);
}
```

## Operadores
Los operadores son muy parecidos a los operadores de C o Java. Sin embargo, hay unas pequeñas variaciones:
+ Los operadores `++` y `--` no pueden ponerse delante de las variables, solo detrás.
+ El operador `?` se sustituye por una flecha de la forma `cond -> expr1 : expr2`.

## Tipos

| Type          | Values                                 | Size (bits) |
| ------------- | -------------------------------------- | ----------- |
| `bit`, `bool` | 0, 1, false, true                      | 1           |
| `byte`        | 0 ... 255                              | 8           |
| `short`       | −32768 ... 32767                       | 16          |
| `int`         | −2<sup>31</sup> ... 2<sup>31</sup> − 1 | 32          |
| `unsigned`    | 0 ... 2<sup>n</sup> − 1 (n ≤ 32)       | ≤ 32        |

### Mtype
Existe un tipo especial que se escribe como `mtype`. Permite añadir valores simbólicos. Cada valor es un entero con valor 1 inicialmente. El problema es que solo se puede definir una vez por programa.

```c
mtype = { REQUEST, ACK, DONE }  // Definimos tres mensajes simbólicos

active proctype sender() {
    mtype msg;   // Variable para almacenar el mensaje

    msg = REQUEST;
    printf("Mensaje enviado: REQUEST\n");

    msg = ACK;
    printf("Mensaje enviado: ACK\n");

    msg = DONE;
    printf("Mensaje enviado: DONE\n");
}

active proctype receiver() {
    mtype msg;

    msg = REQUEST;
    if
    :: (msg == REQUEST) -> printf("Mensaje recibido: REQUEST\n");
    :: (msg == ACK) -> printf("Mensaje recibido: ACK\n");
    :: (msg == DONE) -> printf("Mensaje recibido: DONE\n");
    fi;
}
```

### Printf
Para imprimir los tipos con printf se usa la misma sintaxis que en C:

```c
mtype = { REQUEST, ACK, DONE }  // Definimos tres constantes de tipo mtype

init {
    // Variables de diferentes tipos
    int decimal_val = 42;            // Decimal
    mtype mensaje = REQUEST;         // mtype
    byte caracter = 'A';             // Caracter
    unsigned int_val = 255;          // Unsigned integer

    // Mostrar un solo carácter
    printf("Caracter: %c\n", caracter);  // Muestra: 'A'

    // Mostrar un valor decimal
    printf("Valor decimal: %d\n", decimal_val);  // Muestra: 42

    // Mostrar una constante mtype
    printf("Mensaje mtype: %e\n", mensaje);  // Muestra: REQUEST

    // Mostrar un valor en octal
    printf("Valor octal: %o\n", int_val);  // Muestra: 377 (octal de 255)

    // Mostrar un valor unsigned integer
    printf("Valor unsigned: %u\n", int_val);  // Muestra: 255

    // Mostrar un valor hexadecimal
    printf("Valor hexadecimal: %x\n", int_val);  // Muestra: ff
}
```

## Sentencia if-else
El if-else en Promela es no determinista. Elige aleatoriamente una de las condiciones verdaderas y la ejecuta. Si todas las condiciones son falsas se queda esperando. La sintaxis es:

```c
init {
    int x = 7;

    if
    :: (x < 5) -> printf("x es menor que 5\n");
    :: (x >= 5) -> printf("x es mayor o igual a 5\n");
    fi;
}
```

Por ejemplo, en este código i=0 y x no está inicializado. Al ejecutarlo salta un timeout, ya que como todas las condiciones son falsas el sistema ya no puede seguir.

```c
init {
    int i=0, x; 
    if
    :: i>1 -> x=1
    :: i==5 -> x=2
    :: i<0 -> x=3
    fi;
    printf("x=%d\n", x);
}
```

### Simulación de la cláusula else
La cláusula else realmente es una negación de todas las cláusulas anteriores. Siempre se debe incluir para evitar timeouts. Se puede hacer con un skip:

```c
if 
	:: i==0 -> j++ 
	:: i!=0 -> skip 
fi
```

También se puede poner `else` directamente:

```c
if 
	:: i==0 -> j++ 
	:: else -> skip
fi
```

### Ejemplo: programa no determinista
Este programa se mete en cualquier de las 2 ramas del if de forma aleatoria. Si se ejecuta varias veces se puede ver que el resultado varía:

```c
init {
    int a = 3, b = 3, max, branch;

    if
    :: a >= b -> max = a; branch = 1
    :: a <= b -> max = b; branch = 2
    fi;

    printf("max=%d, branch=%d\n", max, branch);
}

// En 5 ejecuciones printea, por ejemplo:
// max=3, branch=1
// max=3, branch=1
// max=3, branch=2
// max=3, branch=1
// max=3, branch=2
```

### Ejercicio 1: crea un programa que muestre x=1, x=2 o x=3 de forma no determinista

```c
init {
	int a = 0, x;

	if 
		:: a != 1 -> x = 1
		:: a != 2 -> x = 2
		:: a != 3 -> x = 3
	fi;

	printf("x = %d", x);
}
```

## Bucles
Los bucles también son no deterministas. Si una de las condiciones del bucle tiene un `break`, se sale del bucle. 

```c
init {
    int x = 0;

    do
    :: x < 5 -> 
        printf("x = %d\n", x);
        x = x + 1
    :: x >= 5 -> 
        printf("x has reached the limit: %d\n", x);
        break
    od;

    printf("Exited the loop. Final value of x = %d\n", x);
}
```

### Ejercicio 2: crea un programa que muestre todos los números del 1 al 10

```c
init {
	int x = 0;
	do
		:: x != 10 -> x = x + 1; printf("x = %d", x);
		:: x == 10 -> break;
	od;
}
```

### Ejemplo: combinación de bucles y condicionales

```c
mtype = {red, yellow, green};
mtype light = green;

init {
    do
    :: if
        :: light == red -> light = green
        :: light == yellow -> light = red
        :: light == green -> light = yellow
    fi;
    printf("The light is now %e\n", light)
    od;
}
```

Al ejecutar este código con `spin tlight.pml` se obtiene un bucle infinito. Se pueden limitar las ejecuciones con `spin -u40 tlight.pml`. 

Si eliminamos una de las condiciones, el bucle iterará hasta que se no coincida con ninguna rama. Cuando no pueda seguir, saldrá con un timeout avisando del valor que tiene la variable `light` en ese momento.

### Ejemplo: algoritmo de Euclides

```c
init {
    int x = 15, y = 20;
    int a = x, b = y;
    
    do
	    :: a > b -> a = a - b
	    :: b > a -> b = b - a
	    :: a == b -> break
    od;
    printf("The GCD of %d and %d is = %d\n", x, y, a);
}
```

## Statement conditions
Se puede usar una condición como una sentencia normal. Por ejemplo:

```c
int x = 1;

init {
	(x>0);
	printf("%d\n",x);
}
// Muestra el valor 1
```

```c
int x = 1;

init {
	(x>0);
	printf("%d\n",x);
}
// No se cumple la condición y sale con un timeout
```

### Ejercicio 3: crea un programa que muestre, de forma no determinista, cualquier número entre 1 y una constante N

```c
define N 10

init {
	int i = 1; 
	
	do 
		:: (i <= N) -> printf("Number: %d\n", i); break; 
		:: (i < N) -> i = i + 1;
	od;
}
```

## Assert
La cláusula assert sirve para comprobar una condición y, si no se cumple, para la ejecución y muestra la condición violada. Por ejemplo:

```c
init {
    int x = 15, y = 20;
    int a = x, b = y;
    
    do
	    :: a > b -> a = a - b
	    :: b > a -> b = b - a
	    :: a == b -> break
    od;
    printf("The GCD of %d and %d is = %d\n", x, y, a);
    assert(x % a == 0 && y % a == 0);
}
```

### Ejercicio 4: encuentra la postcondición

```c
init {
    int x = 15, y = 4;
    int q, r;
    
    assert (x >= 0 && y > 0); // precondition
    
    q = 0;
    r = x;
    
    do
    :: r >= y -> q++; r = r - y
    :: else -> break
    od;
    
    printf("%d/%d = %d; remainder %d\n", x, y, q, r);
    
    assert (x == q * y + r && r >= 0 && r < y); // postcondition
}
```

## Verificación exhaustiva
Si tenemos un programa no determinista con una aserción, a veces puede no saltar. Sin embargo, si en algún momento puede saltar, se dice que el programa está mal. Esto ocurre cuando SPIN trabaja en modo simulación. Por ejemplo:

```c
init {
    int a = 3, b = 3, max;

    if
	    :: a >= b -> max = a
	    :: a <= b -> max = b + 1
    fi;

    assert (max == a || max == b) && max >= a && max >= b;
}
// Rama 1: a = 3, b = 3, max = 3 (no salta la aserción)
// Rama 2: a = 3, b = 3, max = 4 (salta la aserción ya que no se cumple la primera condición)
```

Para lanzar la verificación exhaustiva podemos hacer `spin -search max.pml` o podemos generarla con C:

```
spin -a max.pml 
gcc -o pan pan.c 
pan
```




