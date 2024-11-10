# Informe P1-SPIN

> [!NOTE] Autores
> Iván Álvarez Fernández,  ivan.alvarez.fernandez
> Antonio Parada Miranda, a.paradam
---

$\space$
### Objetivo 1: Ausencia de deadlocks
El valor más alto de CAP con el cual el sistema presenta deadlocks es 6 (con un valor inicial de 7, nunca se produce un deadlock). Ejecutando el programa con CAP = 6 se produce un timeout.

Se buscamos la traza con CAP=6 y ejecutamos los siguientes comandos:

```
spin -a bank.pml
gcc -o pan pan.c
./pan
```

![[traza1pan.jpg]]

El problema sucede cuando los 3 clientes deciden pedir al mismo tiempo y no hay dinero en la banca (cash = 0).  Como una de las condiciones para poder pedir un préstamo es no haber llegado aún al máximo particular del cliente, este podrá pedir incluso cuando está tan solo 1 unidad por debajo del máximo. Si coincide que los 3 procesos están en esta situación, tendríamos esta disposición en cuanto al dinero de los clientes: {1,3,2}.

Como vemos, la suma del dinero de todos los clientes es 6. Teniendo una configuración inicial de CAP = 6, dada la situación anterior, el banco se queda sin cash. Por tanto, los 3 clientes se quedan esperando por su petición indefinidamente, apareciendo un deadlock (ya que nadie puede resolver el conflicto devolviendo dinero al banco).
#### Conclusión:
Con que la banca tenga 1€ más que esta cantidad (CAP = 7), este problema se solucionaría. Llegados a esa situación extrema en la que los 3 clientes están pidiendo 1€ más cada uno, el banco todavía tendría un mínimo de 1€ disponible, que se le podría otorgar a uno de los clientes. De esta forma, dicho cliente llegaría a su máximo préstamo, teniendo que devolverlo inmediatamente después. Gracias a esto, la banca tendría dinero y podría responder a las peticiones de los otros clientes.
$\space$
### Objetivo 2: Condiciones de safety
**Condición 1: El "cash" siempre vale entre 0 y CAP**
En lógica temporal, esta condición se representa de la siguiente forma: 
$$\square (\text{cash} \geq 0 \land \text{cash} \leq \text{CAP})
$$
$\space$
$\space$
Como queremos tratar de encontrar un contraejemplo, negamos la fórmula y ejecutamos los siguientes comandos:

```
spin -a -f '![](cash >= 0 && cash <= CAP)' bank.pml
gcc -o pan -DSAFETY pan.c
./pan -E -m1400000
```

Como podemos ver en la salida del comando, no se han encontrado errores, por lo que la condición de safety se cumple.

![[traza2.jpg]]
$\space$
**Condición 2: Cada cuenta loan[\_pid] tiene siempre entre 0 y max[\_pid]**

En lógica temporal, esta condición se representa de la siguiente forma: 
$$\square (\text{loan}[\_pid] \geq 0 \land \text{loan}[\_pid] \leq \text{max}[\_pid])$$

Como queremos tratar de encontrar un contraejemplo, negamos la fórmula y ejecutamos los siguientes comandos:

```
spin -a -f '![](loan[_pid] >= 0 && loan[_pid] <= max[_pid])' bank.pml
gcc -o pan -DSAFETY pan.c
./pan -E -m1400000
```

Como podemos ver en la salida del comando, no se han encontrado errores, por lo que la condición de safety se cumple.

![[traza3.jpg]]
$\space$
**Condición 3: Después de cada transferencia, la suma cash+loan[0]+loan[1]+loan[2] es igual a CAP**
En este caso, la comprobación de que se cumple la condición se hace mediante sentencias assert, justo después de las líneas de código que representan la transferencia.

+ Pedir préstamo:
```
cash = cash - request;
loan[_pid] = loan[_pid] + request;
assert(cash+loan[0]+loan[1]+loan[2] == CAP);
```

+ Devolver dinero:
```
loan[_pid] = 0;
cash = cash + current_loan;
assert(cash+loan[0]+loan[1]+loan[2] == CAP);
```

Como estos asserts no paran nunca la ejecución del programa, sabemos que la condición se cumple siempre en esos puntos (que son en los que nos interesa saberlo).
$\space$
### Objetivo 3: Condición de liveness
**Condición: Para cualquier cliente \_pid, cuando hace una petición, recibirá el pago en algún momento**

En lógica temporal, esta condición se representa de la siguiente forma: 
$$\square ((\text{Client}[\_pid]@req) \rightarrow (\lozenge (\text{Client}[\_pid]@got)))$$

Las etiquetas "req" y "got" representan una línea concreta del programa:

+ Pedir préstamo ("req"):
```
short request;
select (request: 1 .. max[_pid] - loan[_pid])
req:  printf("C%d requests %d.   %d:[%d,%d,%d]\n", _pid, request, cash, loan[0],loan[1],loan[2]); 
```

+ Recibir préstamo ("got"):
```
cash = cash - request;
loan[_pid] = loan[_pid] + request;
assert(cash+loan[0]+loan[1]+loan[2] == CAP);
got:  printf("C%d got %d.   %d:[%d,%d,%d]\n", _pid, request, cash, loan[0],loan[1],loan[2]);
```

Como queremos tratar de encontrar un contraejemplo, negamos la fórmula y ejecutamos los siguientes comandos:

```
spin -a -f '<>((Client[_pid]@req) && ([]!(Client[_pid]@got)))' bank.pml
gcc -o pan pan.c
./pan -a -f -i
```

La salida del comando nos muestra la existencia de errores. 

![[Imágenes/traza4.jpg]]

Analizando la traza con `spin -t bank.pml`, obtenemos la siguiente descripción:

![[traza4 1.jpg]]

Al ser una condición de liveness, spin nos demuestra la existencia de un error mediante un ciclo, que comienza en la línea "START OF CYCLE". 

En este bucle podemos ver qué situación causa la inanición y, por tanto, incumple la condición de liveness.  Estando dos de los clientes pidiendo un préstamo (esperando a que haya dinero suficiente), si el otro cliente pide su máximo (dejando sin dinero al banco) lo tendrá que devolver. Si justo después decide volver a pedir su máximo, se volverá a la situación inicial. Por tanto, existe una posible ejecución en la que dicho cliente podría estar realizando esas 2 acciones por siempre de manera cíclica, dejando a los otros 2 clientes esperando a recibir su préstamo infinitamente.

### Notas adicionales
La profundidad de búsqueda requerida para este programa es de 1321969. En los casos en los que haga falta cambiar la profundidad por defecto, hay que utilizar la flag -m.

```
./pan -m1400000
```




