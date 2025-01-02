[[Tema 2-El lenguaje CSharp]]

## Qué son los tipos genéricos?
> [!abstract] Definición de generics
> Los generics son una característica del CLR que permite que las clases, structs, interfaces y métodos tengan parámetros de tipo genérico para los tipos de dato que almacenan y manipulan.

```CSharp
public class Box<T>
{
    private T content;

    public void Add(T item)
    {
        content = item;
    }

    public T Get()
    {
        return content;
    }
}

// Ejemplo de uso:
// Box<string> stringBox = new Box<string>();
// stringBox.Add("Hello, World!");
// string result = stringBox.Get(); // result = "Hello, World!"
```

### Ventajas
Se deben utilizar por:
+ Comprueban los tipos en tiempo de compilación.
+ Tienen muy buen rendimiento.
+ Reducen la complejidad del código.