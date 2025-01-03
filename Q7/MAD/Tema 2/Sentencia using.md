[[Tema 2-El lenguaje CSharp]]

## Funcionamiento de using
Los objetos que se deben limpiar después de ser usados. Para ello implementan la interfaz `System.IDisposable` con el método `Dispose()`. La sentencia `using` permite crear una instancia, utilizarla y, al terminal, llamar a este método.

También define un ámbito. Las variables declaradas en él no se pueden usar fuera de este.

```CSharp
using System;
using System.IO;

public class Example
{
    public void WriteToFile(string path, string content)
    {
        using (StreamWriter writer = new StreamWriter(path))
        {
            writer.WriteLine(content);
        }
        // Aquí, el método Dispose() de StreamWriter se llama automáticamente al salir del bloque using.
    }
}
```