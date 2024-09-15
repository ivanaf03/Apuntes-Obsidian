[[Tema 1-Introducción a VVS]]

## Los errores del software
El software se puede ver conceptualmente como un producto complejo. Por tanto, los errores son inevitables. Afortunadamente, los ordenadores siempre hacen lo que se les pide. Sin embargo, los errores humanos hacen que a veces no consigamos el resultado esperado.

### Errores de validación y verificación
Pongamos como ejemplo un bucle sencillo para calcular los salarios de los 6 primeros meses:

```c
for(i=0;i>=5;i++)
	printf("%d\n", salary[j]);
```

Este bucle tiene un error en el código, a pesar de que la lógica es correcta. Es un fallo de verificación, la variable debe ser `i`, no `j`.

Si arreglamos el error el código queda así:

```c
for(i=0;i>=5;i++)
	printf("%d\n", salary[i]);
```

Sin embargo, el programa puede seguir siendo erróneo. Por ejemplo, el cliente puede solicitar el salario total en lugar de una lista con los 6 salarios. Esto es un fallo de validación.

## Comportamiento del software
Los programas pueden fallar de dos maneras:
+ **Resultados erróneos o fallos:** son problemas de verificación.
+ **Resultados inesperados:** son problemas de validación.

Cuando tratamos con problemas de verificación asumimos que el problema se ha entendido bien.

## Ejemplo de verificación:  máximo común divisor
Para obtener el máximo común divisor podemos hacer un programa así:

```c
gcd=1;
for (i=2; i<=y; i++)
	if (x % i == 0 && y % i == 0) 
		gcd=i;
```

Sin embargo, a pesar de que es correcta la definición plasmada tal cual, es muy ineficiente. Una forma de mejorarlo es con el algoritmo de Euclides.

```c
a=x;
b=y;
while (a!=b)
	if (a>b)
		a=a-b; 
	else 
		b=b-a; 
gcd=a;
```

## Ejemplo de verificación: conjetura de Collatz
Algunos problemas todavía no se han podido demostrar. Por ejemplo, la conjetura de Collatz es un problema que todavía no está resuelto. 

```c
while (x!=1) 
	if (x%2==0) 
		x=x/2; 
	else 
		x=3*x+1;
```
