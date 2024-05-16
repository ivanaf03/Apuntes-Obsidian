[[Tema 4-Seguridad]]
$\space$
## 1.Identificadores
Los AuthID son identificadores utilizados para representar usuarios o roles que tienen ciertos niveles de autorización o permisos dentro del sistema de gestión de bases de datos. Pueden ser:
+ Identificadores o nombres de usuario.
+ Nombres de rol.
+ `public`, que referencia a todos los AuthID
$\space$
### 1.1.Identificación con cuenta y nombre de usuario
El nombre o cuenta de usuario es un identificador que se utiliza para conectarse a la BBDD. Identifica a un usuario, persona o programa que accede a la BBDD. En el estándar no se indica como crearlos.

```sql
-- Oracle:
-- Como identificador, si hay caracteres como el punto,
-- el usuario y la contraseña deben ir entre comillas dobles
create user "nombre.usuario" identified by "contraseña..secreta";
-- Identificación externa: SO o LDAP
create user usuario identified externally;

-- PostgreSQL:
-- El usuario debe ir entre comillas dobles si tiene caracteres especiales
-- Pero la contraseña debe ir SIEMPRE entre comillas simples, como un texto
create user "nombre.usuario" with password 'contraseña';

-- SQL Server:
-- Usuario de la BD
create user usuario with password='contraseña';
-- Usuario basado en login
create user usuario from login usuariowindows;
```
$\space$
## 2.Autenticación
La autenticación es el primer proceso que realiza un SGBD para realizar el control de acceso a la BBDD. Consiste en identificar a un usuario y verificar su identidad.
$\space$
### 2.1.Secuencia
Los pasos son:
1. El usuario indica su AuthID, que es su nombre de usuario.
2. Se verifica que el usuario es quien dice ser, generalmente con una contraseña, ya sea con el propio gestor, mediante el SO o con sistemas externos.
3. Autorización
$\space$
## 3.Autorización
La autorización especifica que puede hacer un usuario en la base de datos. Aunque un usuario se autentique eso no le garantiza poder hacer nada en la base de datos. 

Existen dos tipos de mecanismos de control de acceso:
+ **MAC (Mandatory Access Control):** no está definido en el estándar.
+ **DAC (Discretionary Access Control):** está definido en el estándar. Se basa en la concesión y eliminación de privilegios con `grant` y `revoke`. Incluye la autorización basada en roles.
$\space$
### 3.1.MAC
Se basa en políticas del sistema, que no son modificables por los usuarios. Cada objeto de la base de datos tiene una clase de seguridad. Cada usuario tiene un nivel de autorización sobre esa clase. En base a esto un usuario tendrá permisos de lectura o escritura.

La idea es que los datos confidenciales no pasen a un usuario sin el nivel de seguridad adecuado.
$\space$
#### 3.1.1.Ejemplo: modelo Bell-LaPadula
Se definen clases de seguridad: TS(Top Secret), S (Secret), C (Confidential), U (Unclassified). Se dan a los objetos y a los usuarios clases de seguridad. Por ejemplo, TS(tabla1), S(user1).

Este modelo define 2 reglas: 
+ **Simple:** un usuario S puede leer un objeto O si la clase de S es mayor o igual que la clase de 0.
+ **Estrella:** un usuario S puede escribir un objeto O si la clase de S es menor o igual que la clase de O.