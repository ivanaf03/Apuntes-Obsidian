[[Tema 4-Seguridad]]

# 1.AuthID
Los AuthID son identificadores utilizados para representar usuarios o roles que tienen ciertos niveles de autorización o permisos dentro del sistema de gestión de bases de datos. Pueden ser:
+ [>] Identificadores o nombres de usuario.
+ [>] Nombres de rol.
+ [>] `public`, que referencia a todos los AuthID

## 1.1.Identificadores de usuario
Es un identificador de SQL que utiliza para conectarse a la base de datos. Identifica a una persona o programa que accede a la base de datos. No hay un estándar para la creación de nombres de usuario.

```sql
-- En Oracle
create user "nombre" idenfitied by "contraseña";
create user usuario identified externally;
```

```sql
-- En Postgre
create user "nombre" with password 'contraseña';
```

# 2.Autenticación
La autenticación es el primer proceso que realiza el gestor para el control de acceso de los usuarios. Identifica a un usuario y comprueba su identidad. Consiste en:
1. El usuario indica su AuthID.
2. Se verifica que el usuario es quien dice ser, normalmente mediante una contraseña. Puede hacerlo el SGBD o puede hacerse de forma externa, por ejemplo el SO o un LDAP.
3. Se pasa a la fase de autorización.

# 3.Autorización
La autorización es lo qué puede hacer un usuario en la base de datos. Aunque un usuario se autentique, no tiene por que poder siquiera conectarse a la base de datos.

Existen dos tipos de control de acceso:
+ [>] *Control de acceso obligatorio:* no está definido en el estándar.
+ [>] *Control de acceso direccional:* está definido en el estándar.

## 3.1.Control de acceso obligatorio
Se basa en políticas del sistema, por lo que son modificables por el usuario. Se le asigna a cada objeto de la base de datos una clave de seguridad. A cada usuario se le asigna un nivel de autorización para cada clase de seguridad. Los usuarios pueden leer o escribir un objeto basándose en los niveles de autorización y clases de seguridad.

Se basa en garantizar que los datos confidenciales no pasen a un usuario sin el nivel de seguridad adecuado. 

### 3.1.1.Ejemplo: modelo Bell-LaPadula
Se basa en definir clases de seguridad:
+ *TS:* top secret
+ *S:* secret
+ *C:* confidential
+ *U:* unclassified

$\space$
Asigna una clase de seguridad a los objetos y a los usuarios y define dos reglas:
+ *Simple:* Un sujeto puede leer un objeto si la clase del sujeto es mayor o igual que la del objeto.
+ *Estrella:* Un sujeto puede escribir un objeto si la clase del sujeto es menor o igual que la del objeto.