[[Tema 5-Enterprise Library]]

## Para qué sirve?
El Logging Application Block permite generar eventos de log en diferentes destinos sin necesidad de modificar el código. Pueden enviarse a múltiples sitios, desde guardarse en BBDD hasta enviarse por correo. Permite ser configurado en tiempo de ejecución. 

Contiene un sistema de filtros. Permite filtrar los mensajes en base a la categoría.

### Uso desde código

```csharp
LogEntry entry = new LogEntry(); 

entry.Message = "Mensaje a registrar"; 
entry.Severity = System.Diagnostics.TraceEventType.Critical; 
entry.Categories.Add("General"); 

Logger.Write(entry);
```

No se indica el destino del log desde código, esto se realiza en la configuración. La configuración genera un fichero XML.

## LogManager
Es una clase del `ModelUtil` que implementa la funcionalidad de log. Simplifica el sistema de logs mediante la clase `Logger`. Declara 3 tipos de logs: info, warning y error.

```csharp
public sealed class LogManager
{
    private const string DefaultGeneralCategory = "General";
    private const MessageType DefaultMessageType = MessageType.Error;
    private static LogWriter logWriter;

    static LogManager()
    {
        LogWriterFactory logWriterFactory = new LogWriterFactory();
        logWriter = logWriterFactory.Create();
    }

    public static void RecordMessage(String message)
    {
        RecordMessage(message, DefaultMessageType, DefaultGeneralCategory);
    }

    public static void RecordMessage(String message, MessageType messageType)
    {
        RecordMessage(message, messageType, "General");
    }

    public static void RecordMessage(String message, MessageType messageType, string category)
    {
        if (logWriter.IsLoggingEnabled())
        {
            Console.WriteLine("[" + DateTime.Now.ToString() + "] " + "(" + messageType.ToString() + ") : " + message);

            LogEntry entry = new LogEntry();
            entry.Message = message;
            entry.Severity = (TraceEventType)messageType;
            entry.Categories.Add(category);
            logWriter.Write(entry);
        }
    }
}

```

Un ejemplo de uso sería:

```csharp
LogManager.RecordMessage("Esto es un mensaje de ERROR");

LogManager.RecordMessage("Esto es un mensaje informativo", MessageType.Info); 

LogManager.RecordMessage("Esto es un mensaje informativo de categoría 'General'", MessageType.Info, "General");
```