[[Tema 1-Introducción a VVS]]

## Errores en el software
El software se puede ver como un producto, pero no es un objeto físico. Es mucho más complejo, por lo que es muy frecuente que tenga errores.

Por suerte, los ordenadores se comportan siempre igual, son deterministas. El fallo está en que muchas veces nos equivocamos en lo que pedimos al ordenador. Los errores humanos son los que hacen que el resultado no sea el esperado.

### Errores de validación y verificación
Por ejemplo, si queremos hacer un bucle que muestre el salario para los primeros 6 meses del año podemos hacer algo así:

```c
for(i=0;i>=5;i++)
	printf("%d\n", salary[j]);
```

Este bucle tiene un error de verificación, la variable correcta es `i`, no `j`. El programador ha entendido lo que se pedía, pero no lo ha implementado correctamente. 

Se puede corregir así:

```c
for(i=0;i>=5;i++)
	printf("%d\n", salary[i]);
```

Sin embargo, también está mal, porque realmente lo que quería la persona que pidió el programa era que se mostrara la suma de todos los salarios. En este caso es un fallo de validación.

## Comportamiento de un programa
Un programa puede fallar de dos formas:
+ Si tiene fallos inesperados, se habla de verificación.
+ Si el programa no se ajusta a lo que se pide, se habla de validación.

### Verificación
Cuando se habla de verificación solamente se da por hecho que el programa se ajusta a lo que se ha pedido. Por ejemplo, si nos piden realizar un programa que calcule el máximo común divisor podemos utilizar la definición.

```c
gcd=1;
for (i=2; i<=y; i++)
	if (x % i == 0 && y % i == 0) 
		gcd=i;
```

Sin embargo, para calcular el máximo común divisor de dos números grandes el programa es extremadamente ineficiente. Aunque parezca correcto, no lo es del todo, ya que se puede mejorar muchísimo. Una buena forma es con el algoritmo de Euclides.

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

A veces no se puede verificar que algo es correcto. Un ejemplo muy clásico es la conjetura de Collatz. 

```c
while (x!=1) 
	if (x%2==0) 
		x=x/2; 
	else 
		x=3*x+1;
```

No se ha conseguido probar que funcione para cualquier número entero, aunque a priori parezca que si.