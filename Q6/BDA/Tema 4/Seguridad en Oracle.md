[[Tema 4-Seguridad]]
$\space$
## 1.Privilegios
Oracle sigue el estándar quitando algunos aspectos
$\space$
### 1.1.Privilegios sobre objetos
Incluye permisos adicionales para objetos, como `alter`, `audit`, etc. Se pueden ver en `table_privilege_map`. 

Las sentencias `grant` y `revoke` siguen el estándar, pero no es obligatorio poner la palabra `privileges` en el `all`. Además `revoke` siempre se comporta en cascada y no permite eliminar la posibilidad de dar privilegios con `grant option for`, hay que eliminar el privilegio entero para ello.
$\space$
### 1.2.Privilegios de sistema y roles
Oracle utiliza privilegios del sistema mediante unos roles predeterminados. Los roles se activan con `set role`.

Los roles que el sistema trae por defecto son:
+ **Connect:** conectarse a Oracle.
+ **Resource:** crear elementos en el esquema propio.
+ **DBA:** administrador.
+ **Audit_admin:** configurar auditorías del sistema.
$\space$
#### 1.2.3.Características
En Oracle:
+ Crear un usuario no garantiza que este tenga acceso a la BBDD.
+ Los privilegios asociados a un rol no se asignan hasta que el usuario los activa.
+ Al quitar un rol no se eliminan directamente los permisos.
+ Los privilegios tienen efecto inmediato.
+ Si un usuario no tiene privilegio sobre un objeto el gestor dice que no existe.
$\space$
#### 1.2.2.Gestión de roles

```sql
-- BDA
create role rol1;
grant rol1 to usr with admin option;

-- USR
grant rol1 to usr2 with admin option;

-- USR2
grant rol1 to usr3, usr4;
revoke rol1 from usr4, usr;
```

```sql
-- bda: Crear un usuario
create user usr identified by clave quota unlimited on users;

-- usr: Intentar conectar como usr
connect usr/clave;
-- Error: usr no tiene el privilegio create session

-- bda: Otorgar privilegio de conexión (el rol CONNECT contiene el privilegio create session)
grant connect to usr;

-- usr: Intentar conectar nuevamente como usr
connect usr/clave;
-- Conectado (se activó el rol CONNECT en el momento de la conexión)
```

```sql
-- bda: crear un rol llamado creador
create role creador;

-- bda: otorgar el permiso para crear tablas al rol creador
grant create table to creador;

-- bda: asignar el rol creador al usuario usr
grant creador to usr;

-- usr: intentar crear una tabla, falla debido a permisos insuficientes
create table t(x int constraint pk_t primary key);

-- usr: activar el rol creador para obtener los permisos necesarios
set role creador;

-- usr: crear una tabla, ahora tiene los permisos necesarios
create table t(x int constraint pk_t primary key);

-- VERSIÓN 1: Revocar el rol creador
-- bda: revocar el rol creador del usuario usr
revoke creador from usr;

-- usr: intentar crear otra tabla, ahora que se revocó el rol creador
create table t2(x int constraint pk_t2 primary key);

-- usr: activar todos los roles, pero ya no tiene el rol "creador"
set role all;

-- usr: intentar crear otra tabla, falla debido a permisos insuficientes
create table t2(x int constraint pk_t2 primary key);

-- VERSIÓN 2: Eliminar el rol creador
-- bda: eliminar el rol creador
drop role creador;

-- usr: intentar crear otra tabla después de eliminar el rol creador, falla debido a permisos insuficientes
create table t2(x int constraint pk_t2 primary key);

```

```sql
-- usr: intenta crear una tabla, falla debido a privilegios insuficientes
create table t(x int constraint pk_t primary key);

-- bda: otorga el permiso para crear tablas al usuario usr
grant create table to usr;

-- usr: intenta crear una tabla nuevamente, ahora con permisos, la tabla se crea con éxito
create table t(x int constraint pk_t primary key);

-- bda: revoca el privilegio para crear tablas del usuario usr
revoke create table from usr;

-- usr: intenta crear otra tabla después de revocar el privilegio, falla debido a privilegios insuficientes
create table t2(x int constraint pk_t2 primary key);

-- También observamos que Oracle sigue el estándar en cuanto a no poder inferir información a la que no se tiene acceso:
-- Si usr no tiene acceso a la tabla SCOTT.EMP, el error obtenido es "la tabla o vista no existe"
-- usr: intenta seleccionar datos de la tabla SCOTT.EMP, pero falla
select * from scott.emp; -- ERROR en línea 1: ORA-00942: la tabla o vista no existe

-- bda: otorga el privilegio de SELECT en SCOTT.EMP al usuario usr
grant select on scott.emp to usr;

-- usr: selecciona datos de la tabla SCOTT.EMP después de otorgar el privilegio
select * from scott.emp; -- obtiene los datos de la tabla
```
$\space$
## 2.Ejercicios
Ejercicios de permisos en Oracle.
$\space$
### 2.1.Ejercicio 1

```sql
1 (U1) grant select on T to U2 with grant option;
2 (U2) grant select on U1.T to U3 with grant option;
3 (U1) revoke select on T from U3; 
4 (U3) select * from U1.T;
```

Falla la sentencia 3 porque no es U1 el que dio permisos a U3.
$\space$
### 2.2.Ejercicio 2

```sql
1. grant r1 to r2 
2. grant r1 to usuario
3. grant r2 to usuario 
4. revoke r1 from usuario
```

El usuario pierde los permisos de r1. Solo conserva los de r2.
$\space$
### 2.3.Ejercicio 3

```sql
1. (dba) create user usuario identified by "clave";
2. (dba) grant connect to usuario;
3. (dba) grant select on taboa to usuario;
4. (usuario) connect usuario/clave;
5. (dba) revoke connect from usuario;
6. (usuario) select * from dba.taboa;
7. (dba) revoke select on taboa from usuario;
8. (usuario) select * from dba.taboa;
9. (usuario) connect usuario/clave;
```

Falla la sentencia 8, la eliminación de privilegios sobre objetos es directa. Sin embargo, al no usar `kill session`, el usuario podrá seguir conectado aunque le hayan quitando el permiso `connect`.