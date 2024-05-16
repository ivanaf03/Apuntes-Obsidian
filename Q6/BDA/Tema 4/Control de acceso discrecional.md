[[Tema 4-Seguridad]]
$\space$
## 1.Privilegios
El control de acceso discrecional (DAC) se basa en dar y eliminar privilegios. Pueden ser a nivel de sistema o a nivel de objeto. 
$\space$
### 1.1.Privilegios a nivel de sistema
Especifican acciones que un usuario puede hacer sin estar vinculadas con un objeto concreto. Por ejemplo, crear tablas, crear vistas, etc. No están definidos en el estándar. 

Casi todos los gestores lo implementan y suele ser muy parecida a la gestión de roles.
$\space$
### 1.2.Privilegios a nivel de objeto
Están asociados a un objeto concreto. Están definidos en el estándar. Por ejemplo, hacer `select`, `insert`, `trigger`, etc. para tablas y vistas. El creador de un objeto tiene todos los privilegios sobre él y puede pasar privilegios a otros usuarios.

Si un usuario intenta acceder a datos que no tiene acceso, el SGBD dirá que no tiene permisos.
$\space$
#### 1.2.1.Concesión de privilegios
Se utiliza la sentencia `grant`.

```sql
grant { <lista_privilegios> | all privileges }
on <objeto>
to <lista_authids>
[with grant option];
```

Esta sentencia permite dar varios privilegios sobre un objeto, pero a un único objeto. Con `all privilegies` puede dar todos los permisos al usuario. Con `with grant option` permite pasar e privilegio de dar permisos a otro usuario.

Un ejemplo:

```sql
grant select, delete, insert on tab1 to usuario1;

grant update(sal) on emp to scott, role345 with grant option;

grant all privileges on emp to theboss;

grant select on emp to public; -- Todos los usuarios, incluso los creados en el futuro, podrán seleccionar de emp
```
$\space$
#### 1.2.2.Supresión de privilegios
Se utiliza la sentencia `revoke`.

```sql
revoke [grant option for] { <lista_privilexios> | all privileges }
on <obxecto>
from <lista_authids>
{ cascade | restrict };
```

Un usuario solo puede eliminar los privilegios que concedió con `grant`. Con `grant option for` se elimina la capacidad para pasar privilegios a otros usuarios. Si algún usuario pasó el permiso a otros usuarios, con `cascade` se eliminan en cascada, pero con `restrict` se produce un error.

Un ejemplo:

```sql
revoke delete, insert on tab1 from usuario1;

revoke update(sal) on emp from scott cascade;

revoke select on emp from public;
```
$\space$
#### 1.2.3.Cadenas de privilegios
Cada vez que se concede un permiso a un AuthID se establece una línea de concesión. Esto puede terminar en complejas cadenas de concesión de permisos. 

Un AuthID pierde un privilegio si se elimina de todas las líneas de concesión.

![[permisos cadena 1.png]]

![[permisos cadenas 2.png]]
$\space$
## 2.Roles
Un rol es un tipo especial de AuthID que se utiliza para facilitar la gestión de privilegios. Se les puede asignar privilegios u otros roles y se puede dar a los demás AuthIDs un rol con `grant` para que obtengan todos los permisos de este.

```sql
-- Crear roles
create role facturador; -- Crear rol facturador
create role gestor; -- Crear rol gestor

-- Conceder privilegios a roles
grant all privileges on factura to facturador; -- Conceder todos los privilegios en factura al rol facturador
grant select on articulo to facturador; -- Conceder privilegio de SELECT en articulo al rol facturador
grant all privileges on articulo to gestor; -- Conceder todos los privilegios en articulo al rol gestor
grant facturador to gestor; -- Conceder el rol facturador al rol gestor
grant facturador to facturador1, facturador2; -- Conceder el rol facturador a los roles facturador1 y facturador2
grant gestor to gestor1; -- Conceder el rol gestor al rol gestor1

-- Revocar privilegios de roles
revoke facturador from facturador2; -- Revocar el rol facturador del rol facturador2
revoke references on factura from facturador; -- Revocar privilegios de REFERENCES en factura del rol facturador

-- Eliminar rol
drop role gestor; -- Eliminar el rol gestor
```
$\space$
### 2.1.With admin option
Las sentencias `grant` y `revoke` con roles pueden utilizar `with admin option`. Permite a quien se conceda poder administrar este rol:
+ Puede conceder privilegios o otros roles a este rol.
+ Puede dar o quitar el rol a cualquier AuthID.
$\space$
### 2.2.Ejemplo de uso de roles
Tenemos 3 usuarios que necesitan gestionar facturas. Estos pueden seleccionar, insertar, borrar y modificar en las tablas `Factura` y `Liña` y seleccionar de `Artigo`.

Además aparece un cuarto facturador y un gestor que puede gestionar facturas y modificar el precio de los artículos.
$\space$
#### 2.2.1.Sin uso de roles

![[roles 1.png]]

![[roles 2.png]]

![[roles 3.png]]
$\space$
#### 2.2.2.Con uso de roles

![[roles 4.png]]

![[roles 5.png]]

![[roles 6.png]]
