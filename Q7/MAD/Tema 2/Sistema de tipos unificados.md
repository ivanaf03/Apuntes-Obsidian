[[Tema 2-El lenguaje CSharp]]

## Tipos por valor y referencia
Los tipos de datos se pueden pasar por valor o por referencia.

Se pasan por valor:
+ Tipos primitivos
+ Enumeraciones
+ Structs

Se pasan por referencia:
+ Object
+ Strings
+ Clases
+ Interfaces
+ Arrays
$\space$
### Boxing y unboxing
El boxing consiste en la transformación de tipos valor a tipos referencia. Por ejemplo:

```CSharp
int i = 3;
object obj = i;
```

El unboxing es el proceso inverso. Por ejemplo:

```CSharp
int x = (int) obj;
```