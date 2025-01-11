[[Tema 9-Web Forms]]

## Propiedades de Page
Los web forms son instancias de la clase `System.Web.UI.Page`. Tiene ciertas propiedades interesantes.

### Session y Application
Una Session es una instancia de la clase `System.Web.SessionState.HttpSessionState`. Almacena datos del usuario entre solicitudes a distintas páginas mediante pares clave-valor.

Una Application es una instancia de la clase `System.Web.HttpApplicationState`. Sirve para almacenar datos globales de la aplicación, también mediante pares clave-valor.

### Request
Es una instancia de la clase `System.Web.HttpRequest`. Representa valores y propiedades de la solicitud HTTP que hace que se cargue la página. Se puede acceder a esta información desde los controles:
+ **Browser:** información del navegador.
+ **Cookies:** cookies enviadas por la solicitud.
+ **QueryString:** parámetros que se pasan en la consulta.
+ **Url y UrlReferrer:** dirección actual de la página y dirección de la página de la que viene.
+ **UserLanguages:** array de strings con las preferencias del lenguaje del cliente.

### Response
Es una instancia de la clase `System.Web.HttpResponse`. Representa la respuesta del servidor a una solicitud del cliente. Contiene las cookies y el método `Redirect()`, que permite al navegador apuntar hacia otra página.

### Server
Es una instancia de la clase `System.Web.HttpServerUtility`. Sus propiedades son:
+ **HtmlEncode() y HtmlDecode():** convierte un string en caracteres HTML y viceversa.
+ **UrlEncode() y UrlDecode():** convierte un string en una URL y viceversa.
+ **MapPath():** devuelve la ruta física de una ruta virtual del servidor.
+ **Transfer():** transfiere la ejecución a otra página web de forma muy rápida. Solo permite pasar a otras páginas ASP.NET del mismo servidor y aplicación. No cambia la URL del navegador.

### Trace
Es una instancia de la clase `System.Web.TraceContext`. Permite escribir información de log en las páginas con `Trace.IsEnabled = true` en el código o en la directiva `Page` con `Trace="true"`. Muestra los mensajes en el orden en que se generaron. Se pueden ordenar por categoría desde el código o desde la directiva con `TraceMode`. 

Permite escribir mensajes en el log con los métodos `Write()` y `Warn()`. 

Se configura desde el `web.config`:

```xml
<configuration>
    <system.web>
        <trace 
            enabled="true" 
            requestLimit="10" //límite de logs 
            pageOutput="false" //información de la traza en la página
            traceMode="SortByTime" //ordenación por tiempo o categoría
            localOnly="true" //solo en localhost
        />
        ...
    </system.web>
</configuration>
```