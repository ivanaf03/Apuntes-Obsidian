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

a = d * k1
a - b = d * k2
a - b = d * k1 - b
d * k2 = d * k1 - b
b = d * k1 - d * k2
b = d * (k1 - k2)


0 = a - a = a - (a - b) = k1 * d - (k1 * d - k2 * d)
```

El algoritmo para porque al restar un número menor a un número mayor siempre da un número más pequeño que el mayor, por tanto, los valores de a y b van disminuyendo progresivamente. Además, la resta siempre va a dar un número natural. 