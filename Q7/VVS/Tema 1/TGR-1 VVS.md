[[Tema 1-Introducción a VVS]]

## Algoritmo de Euclides
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

Si a es mayor que b, el máximo común divisor de a y b es el mismo que el máximo común divisor de a-b y b. Pasa la inversa cuando b es mayor que a.

Como el mcd es divisor de ambos, también es divisor de la resta. 

```
a = d * k1
b = d * k2

a - b = (d * k1) - (d * k2) = d (k1-k2) = d * k3
```
