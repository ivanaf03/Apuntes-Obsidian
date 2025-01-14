[[Tema 12-Gestión de estado]]

## Cómo se gestiona el estado en el servidor?
El estado del lado servidor se puede manejar mediante:
+ Variables de sesión para el propietario de la sesión.
+ Variables de aplicación para todas las sesiones y usuarios.

### Variables de aplicación
El estado se guarda en una instancia de `HttpApplicationState`. Se puede acceder a él mediante `Page.Application`. Se debe usar solamente en modo lectura. Se inicializa desde el `Global.asax`.

```csharp
// Escritura
Application["Message"] = "Welcome to this site.";

// Las variables de estado de aplicación pueden ser accedidas por
// múltiples threads al mismo tiempo. Para prevenir datos inválidos,
// se debe bloquear el acceso de escritura para que sólo pueda acceder un thread.
Application.Lock();
Application["PageRequestCount"] = ((int)Application["PageRequestCount"]) + 1;
Application.UnLock();

// Lectura
if (Application["AppStartTime"] != null)
{
    DateTime myAppStartTime = (DateTime)Application["AppStartTime"];
}
```

### Variables de sesión
> [!abstract] Definición de sesión
> Una sesión es el contexto donde el usuario se comunica con el servidor a través de peticiones.

HTTP no es orientad a sesiones ni a estado. El concepto de sesión y estado se debe manejar a través de la programación. Se utiliza la clase `HttpSessionState` y se puede acceder a ella mediante `Page.Session`.

```csharp
// Escritura
Session["firstName"] = "Pedro";

// Si se almacenan datos procedentes de un control de entrada, conviene usar
// el método HtmlEncode
Session["firstName"] = Server.HtmlEncode(firstNameTextBox.Text);

// Sintaxis alternativa
Session.Add(itemName, itemValue);

// Lectura
string firstName = Session["firstName"].ToString();

// Alternativa
string firstName = (string)(Session["firstName"]);

// Conviene asegurarse de que el valor está en la sesión
if (Session["firstName"] == null)
{
    ...
}
```

El ID de la sesión es una cadena que se puede guardar en una cookie, `ASP.NET_SessionID`. Otra opción es gestionarla a través de la URL.  Este comportamiento se puede establecer en el `web.config` mediante el atributo `cookieless=UseUri` o `cookieless=UseCookies`. Si se pone a `AutoDetect`, será el navegador el que decida si las permite o no.

El estado se puede almacenar:
+ **In-process:** en memoria.
+ **Out-of-process:** en un servidor de estado, con una base de datos SQLServer. Se debe añadir al `web.config` la propiedad `<sessionState inproc="false" server="serverName" port="42424" />`.

El objeto `Session` contiene las propiedades:
+ **Count:** número de pares almacenados.
+ **Keys:** conjunto de claves almacenadas.
+ **IsNewSession:** indica si la sesión se ha creado durante la carga de la página actual.
+ **SessionID:** identificador.
+ **Timeout:** número de minutos que la sesión puede estar activa.

