[[Tema 11-Aplicaciones ASP.NET]]

## Fichero Global.asax
Sirve para escribir manejadores que reaccionan a eventos globales de la aplicación. No se puede llamar directamente, el código se ejecuta al responder a eventos. Solo se puede tener un `Global.asax` por aplicación y se coloca en el directorio raíz.

Los métodos de este archivo tienen nombres predefinidos. 

### Global.asax.cs
```csharp
public class Global : System.Web.HttpApplication
{
    protected void Application_Start(object sender, EventArgs e)
    {
    }

    protected void Session_Start(object sender, EventArgs e)
    {
    }

    protected void Application_BeginRequest(object sender, EventArgs e)
    {
    }

    protected void Application_AuthenticateRequest(object sender, EventArgs e)
    {
    }

    protected void Application_Error(object sender, EventArgs e)
    {
    }

    protected void Session_End(object sender, EventArgs e)
    {
    }

    protected void Application_End(object sender, EventArgs e)
    {
    }
}
```

## Eventos
Se pueden manejar dos tipos de eventos:
+ Eventos que ocurren siempre para cada request.
+ Eventos que ocurren solo bajo ciertas condiciones.

![[ciclo_eventos.png]]

### Eventos que ocurren en cada request
En cada request se ejecutan:
+ **Application_BeginRequest():** se llama al iniciar la request.
+ **Application_AuthenticationResquest():** se llama antes de la autenticación.
+ **Application_AuthorizeRequest():** determina los permisos del usuario.
+ **Application_ResolveRequestCache():** compila e instancia la página. Se usa conjuntamente con la caché de salida. 
+ **Application_AcquireRequestState():** se llama antes de recuperar información de la sesión.
+ **Application_PreRequestHandlerExecute():** ejecuta la request. Se llama antes de hacer la request HTTP.
+ **Application_PostRequestHandlerExecute():** se llama después de manejar la request.
+ **Application_ReleaseRequestState():** se llama cuando se va a serializar la información de la sesión para que esté disponible en la próxima solicitud.
+ **Application_UpdateRequestCache():** se llama antes de añadir información a la caché de salida.
+ **Application_EndRequest():** se llama al final de la request, antes de liberar los objetos.

### Eventos que no se lanzan en cada request
En otros casos se lanzan:
+ **Application_Start():** se lanza al iniciar la aplicación.
+ **Session_Start():** se lanza al iniciar una nueva sesión. Se suele usar para inicializar información del usuario.
+ **Application_Error():** se invoca en excepciones no controladas.
+ **Session_End():** se invoca si termina la sesión del usuario.
+ **Application_End():** se llama antes de que la aplicación termine. 
+ **Application_Disposed():** se llama para que el recolector libere la memoria, después de terminar la aplicación.