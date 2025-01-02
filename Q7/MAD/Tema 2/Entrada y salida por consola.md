[[Tema 2-El lenguaje CSharp]]

## Entrada
Para introducir valores por consola se pueden usar:
+ **Console.Read():** lee un caracter y guarda el Unicode.
+ **Console.ReadLine():** lee una línea.
+ **Console.ReadKey():** lee información de la tecla que se presiona.

## Salida
Para mostrar valores por consola se puede usar.
+ **Console.Write():** escribe sin salto de línea.
+ **Console.Write():** escribe y añade al final un salto de línea.

```CSharp
// ejemplo con console.write 
Console.Write("este texto está en la misma línea, "); 
Console.Write("porque se usó Console.Write. "); 

// ejemplo con console.writeline Console.WriteLine(); 
Console.WriteLine("este texto está en una nueva línea,"); 
Console.WriteLine("porque se usó Console.WriteLine.");
```

### Formatos de salida
Se pueden especificar formatos para los números en la salida por consola:
+ **C:** moneda.
+ **D:** decimal.
+ **F:** punto fijo.
+ **P:** porcentaje.
+ **H:** hexadecimal.

```CSharp
double numero = 1234.56789;

Console.WriteLine($"en formato moneda: {numero:C}");  // en formato moneda: $1,234.57
Console.WriteLine($"en notación científica: {numero:E}");  // en notación científica: 1.234568E+003
Console.WriteLine($"en formato numérico: {numero:N}");  // en formato numérico: 1,234.57
```

También se puede utilizar una convención similar para los formatos de las fechas.