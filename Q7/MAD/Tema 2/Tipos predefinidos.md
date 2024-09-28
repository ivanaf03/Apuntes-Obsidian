[[Tema 2-El lenguaje CSharp]]

## Tipos básicos
Los tipos básicos en C# sin alias a tipos que proporciona el sistema operativo. Estos tipos son:
+ Reference: `object, string`
+ Signed: `sbyte, short, int, long`
+ Unsigned: `byte, unshort, uint, ulong`
+ Character: `char`
+ Floating-point: `float, double, decimal`
+ Logical: `bool`
$\space$
### Sufijos
Cuando tenemos dos métodos con el mismo nombre, pero que reciben un parámetro de distinto tipo, para diferenciarlos debemos usar sufijos. Estos son:
+ L:  `long, ulong`
+ U: `int, uint`
+ UL: `ulong`
+ F: `float`
+ D: `double`
+ M: `decimal`

Por ejemplo:

```CSharp
public static void Foo (int x) {}
public static void Foo (double x) {}

Foo (100D); //llamada al segundo método
```