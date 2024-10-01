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

Por ejemplo, en este código i=0 y x no está 

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

