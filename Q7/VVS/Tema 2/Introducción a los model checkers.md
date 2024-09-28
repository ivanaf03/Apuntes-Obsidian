[[Tema 2-Model checkers]]

## Programación concurrente
Tenemos dos procesos, P y Q, que pueden incrementar el valor de una celda de memoria de forma concurrente:

```c
P {
	int regP = 0;
	p1: load n into regP;
	p2: regP++;
	p3: store regP into n;
	p4: end;
}

Q {
	int regQ = 0;
	q1: load n into regQ;
	q2: regQ++;
	q3: store regQ into n;
	q4: end;
}
```

El estado se puede ver como el valor de los dos registros, la celda de memoria y el puntero de instrucción de P y Q. Se puede representar como (P, Q, regP, regQ, n). El estado inicial es (p1, q1, 0, 0, 0). Los valores de P y Q pueden ser p1, p2., p3, p4 y q1, q2, q3 y q4. Los valors de regP, regQ y n pueden ser 0, 1 y 2. Esto se puede representar como un autómata finito no determinista con 4 x 4 x 3 x 3 x 3 estados.

Los problemas reales tienen un número finito de valores y, por tanto, siempre se pueden representar de esta manera. Sin embargo, a veces el número de casos posibles totales es gigante. La clave es que no todos los estados se alcanzan. Por ejemplo, en el caso anterior realmente solo se pueden alcanzar de los 432 estados posibles, 22.

### Representación

![[automata de estados pqnppqq.png]]

Un ejemplo de una ejecución es un camino del autómata. Por ejemplo:

```c
(p1, q1, 0, 0, 0)
(p2, q1, 0, 0, 0)
(p3, q1, 1, 0, 0)
(p4, q1, 1, 0, 1)
(p4, q2, 1, 1, 1)
(p4, q3, 1, 2, 1)
(p4, q4, 1, 2, 2)
```

## Comprobación de propiedades
Para comprobar una propiedad hay que encontrar caminos en el autómata. Por ejemplo, podemos comprobar que n = 2. Esto se puede representar como:

$$
p4 \land q4 \implies n = 2
$$

Para comprobar que eso es cierto no debe haber ningún contraejemplo. Sin embargo, uno de los 3 estados finales del autómata termina en (p4, q4, 1, 1, 1). Por tanto, no siempre se cumple la propiedad.

### Comprobación con SPIN
Se puede comprobar con SPIN mediante el siguiente código en Promela:

```c
byte n=0;

active [2] proctype P() {
	byte reg = 0;
	reg = n;
	reg++;
	n = reg;
}
```
