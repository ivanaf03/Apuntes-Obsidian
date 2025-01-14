[[Tema 13-Autenticación y control de acceso]]

## Qué es la autenticación?
> [!abstract] Definición de autenticación
> La autenticación es el proceso mediante el cual se comprueba que alguien es quién dice ser mediante unas credenciales.

## Autenticación ISS
En el Internet Information Server se pueden seleccionar diferentes modos de autenticación:
+ **Anónimo:** el servidor no realiza autenticación. El control se delega en ASP.NET.
+ **Básica:** usuario y contraseña.
+ **Digest:** contraseña hasheada.
+ **Certificados digitales:** el cliente necesita un certificado digital.
+ **Integrada:** credenciales de cuenta de Windows.

## Autenticación ASP.NET
ASP.NET también permite varios modos de autenticación:
+ **None:** acceso anónimo permitido a toda la aplicación web.
+ **Windows:** delega la autenticación en el ISS.
+ **Forms:** autenticación basada en formularios.
+ **Passport:** autenticación a través de Web MS Passport.

### Autenticación basada en formularios
Se indica a ASP.NET donde se redirige al usuario en caso de que solicite acceso a un recurso protegido. Normalmente, se hace a una página para introducir las credenciales. Una vez puestas, se hace una validación. Si son correctas, se genera un ticket de autenticación que se guarda en una cookie.

Se configura con el ISS en modo anónimo y se añade al `web.config`:

```csharp
<configuration>
  <system.web>
    <authentication mode="Forms">
      <forms
        name=".ASPXAUTH"
        loginUrl="/Authentication.aspx"
        timeout="30"
        path="/"
        defaultUrl="/MainPage.aspx"
        cookieless="AutoDetect" />
    </authentication>
  </system.web>
</configuration>
```

El usuario se puede validar mediante:
+ El método `System.Web.Security.FormsAuthentication.Authenticate()` validando contra definiciones del `web.config`.
+ Utilizando un método propio.
+ Mediante la API `Membership`.

### Métodos de FormsAuthentication
El ticket de autenticación se genera y se envía a la aplicación a través de `FormsAuthentication`. Tiene los métodos:
+ **RedirectFromLoginPage():** marca al usuario como autenticado suponiendo que las credenciales ya han sido comprobadas. Crea un ticket en una cookie temporal o persistente, en función del valor de `createPersistentCookie`. Después, redirige a la página solicitada.
+ **SetAuthCookie():** crea una cookie de autenticación y la añade a la response suponiendo que las credenciales ya han sido comprobadas, pero no redirige.
+ **GetAuthCookie():** lo mismo que la anterior, peor no la añade a la response.
+ **SignOut():** elimina el ticket.

