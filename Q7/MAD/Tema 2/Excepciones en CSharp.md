[[Tema 2-El lenguaje CSharp]]

## Qué son las excepciones?
> [!abstract] Definición de excepción
> Un excepción es un mecanismo que permite gestionar errores inesperados.

No pueden ser ignoradas. No es obligatorio gestionarlas en el punto donde ocurren, pueden llevarse a capas superiores. Existen excepciones estándar ya definidas. 

En C# no existe `throws`, por lo que se deben documentar con xml. Las excepciones son instancias de `System.Exception` que se pueden lanzar con `throw` para ser capturadas.

### Captura de excepciones
Para capturar las excepciones se utiliza `try-catch-finally`. Se pueden utilizar varios bloques `catch`.

```CSharp
public class Example
{
    public void Divide(int a, int b)
    {
        try
        {
            int result = a / b;
            Console.WriteLine("Resultado: " + result);
        }
        catch (DivideByZeroException)
        {
            Console.WriteLine("Error: No se puede dividir por cero.");
        }
        finally
        {
            Console.WriteLine("Bloque finally ejecutado.");
        }
    }
}
```
