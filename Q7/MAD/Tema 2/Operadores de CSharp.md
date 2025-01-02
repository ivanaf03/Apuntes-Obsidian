[[Tema 2-El lenguaje CSharp]]

## Operadores
Los operadores son muy similares al de resto de lenguajes:
+ **Aritméticos:** +, -, \*, /, %.
+ **Asignación:** +=, -=, \*=, /=, %=, ++, --.
+ **Comparación:** \==, !=, <, >, <=, >=
+ **Lógicos:** &, &&, |, ||, ~, !, ^.

### Información sobre tipos
El operador `typeof` permite conocer el tipo de una variable.

```CSharp
Type t = typeof(string); 
Console.WriteLine(t); // salida: System.String
```

El operador `is` verifica si un objeto es de un tipo específico.

```CSharp
object obj = 123; 
if (obj is int) { 
	Console.WriteLine("obj es un int."); // salida: obj es un int. 
}
```

El operador `as` permite realizar un casting. Si falla, en lugar de devolver una excepción, devuelve `null`.

```CSharp
object obj = "texto"; 
string str = obj as string;
if (str != null) {
	Console.WriteLine($"obj fue casteado a string: {str}"); // salida: obj fue casteado a string: texto
}
```

