[[Tema 13-Autenticación y control de acceso]]

## Qué es la autorización?
> [!abstract] Definición de autorización
> La autorización es el proceso que determina qué puede hacer cada usuario en una aplicación. También se llama control de acceso.

Se realiza en el `web.config`. Se pueden indicar:
+ **\*:** todos los usuarios.
+ **?:** usuarios no autenticados.

```xml
<configuration>
	<location path="Register.aspx">
	  <system.web>
	    <authorization>
	      <allow users="*" />
	    </authorization>
	  </system.web>
	</location>
</configuration>
```

## Políticas de acceso
Se suelen usar dos políticas:
+ **Restrictiva:** todo lo que no está permitido, está prohibido. Se deniega el acceso a todos los usuarios anónimos y se da acceso a los recursos que no necesitan autenticación.
+ **Permisiva:** todo lo que no está prohibido, está permitido. Se permite el acceso a todos los recursos y se indican aquellos que necesitan autenticación.
