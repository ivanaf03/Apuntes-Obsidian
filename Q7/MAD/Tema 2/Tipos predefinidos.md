[[Tema 2-El lenguaje CSharp]]

## Tipos básicos de C#
Los tipos básicos son alias a tipos que proporciona el propio sistema operativo. Estos son:
+ **Reference:** string y object.
+ **Signed:** sbyte, short, int y long.
+ **Unsigned:** byte, ushort, uint, ulong.
+ **Character:** char
+ **Floating point:** float, double, decimal.
+ **Logical:** bool.

### Sufijos y problemas con métodos del mismo nombre
Si hay dos métodos que se llaman igual, pero que reciben un parámetro de distinto tipo, por defecto se llama al valor más pequeño que permite almacenar el número.

```CSharp
public static void M0(uint x){}
public static void M1 (int x){} // Foo(1) llamaría a este método
public static void M2(long x){}
```

Para evitar esto se pueden utilizar los sufijos:
+ **L:** long, ulong
+ **U:** int, uint.
+ **UL:** ulong.
+ **F:** float.
+ **D:** double.
+ **M:** decimal.

Ahora, una llamada `Foo(1L)` llamaría al método `M2`. 