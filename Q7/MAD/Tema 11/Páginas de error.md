[[Tema 11-Aplicaciones ASP.NET]]

## Excepciones
Cuando se generan excepciones controladas, no pasa nada, las maneja el usuario. Sin embargo, las no controladas van encapsuladas en un `InternalErrorException`. Cuando esto ocurre, se puede redirigir al usuario a una página de error. 

Se pueden definir en dos niveles:
+ Con el atributo `PageError` para indicar que página se lanza.
+ En la sección de `customErrors` del `web.config`. esto permite definir respuestas a códigos HTTP.

```xml
<customErrors mode="RemoteOnly" defaultRedirect="InternalError.aspx">
	<error statusCode="403" redirect="NoAccess.htm" />
	<error statusCode="404" redirect="FileNotFound.htm" />
</customErrors>
```

### Atributo mode
El atributo mode puede tomar varios valores:
+ **On:** se utiliza en producción. Habilita los errores personalizados con el atributo `defaultRedirect`.
+ **Off:** se utiliza en desarrollo. Muestra los errores estándar.
+ **RemoteOnly:** especifica que solo se muestren los errores personalizados en clientes remotos.