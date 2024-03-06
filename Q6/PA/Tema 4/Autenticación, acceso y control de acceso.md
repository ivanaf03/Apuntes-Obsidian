[[Tema 4-Capa de servicios REST con Spring]]

# 1.Paso de id de usuario de forma segura
Algunas peticiones requieren conocer el id de usuario. Es necesario un esquema que permita pasar este id del backend al frontend de forma segura. 

![[esquema autenticacion.png]]

Autenticarse consiste en introducir usuario y contraseña. Si es correcto devuelve una lista de caracteres, un `token`, que se devuelve al bakend y autoriza al usuario para hacer peticiones. Incluye el id del usuario.

Todas las peticiones que requieran el id del usuario tienen que incluir el `token`. Cuando se hace una peticiones se hace el control de acceso. Consiste en validar el token y comprobar que el usuario tiene permitido realizar esa petición.

# 2.JWT
Para generar un `token` utilizaremos JSON Web Token. Define un formato compacto para transmitir JSON entre dos partes de forma segura. 

Los `token` tienen el formato `cabecera.cuerpo.firma`:
+ [>] *Cabecera:* tipo de `token` y algoritmo de firma. Está codificado en base64url.
+ [>] *Cuerpo:* información sobre una entidad en base64url.
+ [>] *Firma:* algoritmo de firma (`cabecera.cuerpo`) en base64url.

![[jwt.png]]

