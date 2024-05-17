[[Tema 4-Seguridad]]
$\space$
## 1.Qué es una auditoría?
Una auditoría de base de datos es un proceso de evaluación sistemática y rigurosa que analiza la seguridad, integridad y eficiencia de una base de datos. Permite registrar información de eventos globales del sistema y acciones que los usuarios hacen sobre los objetos.

Además también se hacen auditorías sobre los logs para detección de intrusos o abusos en el acceso a datos.
$\space$
### 1.1.Qué se audita?
Se auditan:
+ El acceso de usuarios.
+ Los privilegios del sistema.
+ Las modificaciones en el esquema de BBDD.
+ Las modificaciones en datos sensibles.
$\space$
## 2.Auditorías de Oracle
Oracle permite:
+ Oracle audit
+ Triggers del sistema
+ Triggers de inserción y borrado
+ Auditorías detalladas
+ Logs
$\space$
### 2.1.Oracle Audit
Permite auditar todos los permisos que se pueden dar a un usuario. Por ejemplo:

```sql
audit alter table;
audit create sesion; 
audit alter user; 
noaudit drop table;

-- Se puede ver en el catálogo lo que se audita
select audit_option, success, failure from dba_stmt_audit_opts union all
select audit_option, success, failure from dba_priv_audit_opts;
```

También se pueden auditar sesiones:

```
select username, terminal, action_name, to_char(timestamp, 'ddmmyyyy:hhmmss') as timestamp, to_char(logoff_time, 'ddmmyyyy:hhmmss') as logoff_time, returncode from dba_audit_session;
```

![[audit.png]]
$\space$
### 2.2.Triggers del sistema
Se pueden crear triggers para registrar los accesos a la base de datos.

```sql
create table conexiones (
  usuario char(20),
  data_hora timestamp,
  tipo char(12)
);

create or replace trigger log_conexion
after logon on database
begin
  insert into conexiones (usuario, data_hora, tipo)
  values (user, sysdate, 'conexión');
end log_conexion;
/

create or replace trigger log_desconexion
before logoff on database
begin
  insert into conexiones (usuario, data_hora, tipo)
  values (user, sysdate, 'desconexión');
end log_desconexion;
/

select * from conexions;
-- Nada

disconnect;

connect usuario/*****

select * from conexions;
-- Tabla con información de la hora de conexión y desconexión
```
$\space$
### 2.3.Triggers de inserción y borrado
Podemos auditar los cambios en el sueldo de empleados, por ejemplo:

```sql
create or replace trigger t_log_cambio_sal
after update of sal on emp
for each row
begin
  insert into logcambiosal (usuario, timestamp, empno, sal_ant, sal_novo)
  values (user, sysdate, :new.empno, :old.sal, :new.sal);
end;
/
```

![[trigger insercion borrado.png]]
$\space$
### 2.4.Auditorías de grano fino
Podemos hacerlas con DBMS_FGA. Por ejemplo, si queremos que se registren los accesos a la tabla `dept` 
