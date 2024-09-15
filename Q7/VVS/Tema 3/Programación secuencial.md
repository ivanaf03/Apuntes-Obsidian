[[Tema 3-Promela y SPIN]]

## ¿Qué es Promela?
Promela no es un lenguaje de programación. Es un lenguaje para modelos y especificaciones que permite describir el comportamiento concurrente de un conjunto de procesos.

A partir de un sistema real debemos generar con Promela un modelo y unas condiciones que debe cumplir. SPIN se encarga de comprobar si la salida es correcta o no.

## Hola mundo

```c
init {
	printf("Hello world!\n");
}
```

## Ejemplo: programa simple para calcular unidades, decenas y centenas

```c
init {
	int value=123; 
	int reversed;
	reversed= (value % 10)*100+((value/10)%10)*10+(value/100);
	printf("value=%d,reversed=%d\n",value,reversed)
}
```

## Operadores
Funcionan de forma muy similar a C salvo alguna excepción. Por ejemplo, los operadores `++` y `--` no pueden colocarse antes de un valor ni pueden combinarse, por ejemplo, con el `=`. 

El operador condicional no utiliza la interrogación, sigue el formato `cond -> expr1 : expr2`. 

```c
active proctype P() { 
	int a=1,b=3; 
	int max = (a>=b -> a : b); 
	printf("max=%d\n",max) // 3
}
```

El define funciona como en C. Hay que tener mucho cuidado con las macros, ya que no tiene tipado y simplemente reemplaza el texto al hacer el preprocesado. Para evitar errores se usan paréntesis.