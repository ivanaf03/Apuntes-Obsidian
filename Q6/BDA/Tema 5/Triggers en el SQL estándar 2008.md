[[Tema 5-Bases de datos activas]]
$\space$
## 1.Elementos
Un triggers está formado por el nombre del trigger y el nombre de la tabla. 

Los eventos pueden ser inserciones, borrados o actualizaciones. Los triggers se pueden activar antes o después de los eventos. Además se puede elegir si dispararlos una vez para todo el evento o una vez por cada fila afectada. 

Las condiciones se ponen en el `when`, pero no son obligatorias.

Las acciones deben ser atómicas. No se recomienda hacer operaciones DML en triggers before o sentencias de conexión, control de transacciones o operaciones DDL.
$\space$
### 1.1.Tablas y variables de transición
Contienen valores nuevos y antiguos de los triggers. También se llaman nombres de correlación. Se declaran en la cláusula `referencing`. 

Las variables aplican en `for each row` y las tablas en `for each statement`. No son tablas completas, solo aparecen los valores afectados por el trigger.

![[tablas transición.png]]
$\space$
## 2.Sintaxis y uso de triggers
Para crear un trigger la sintaxis es bastante compleja:

![[sintaxis trigger.png]]

Para borrar un trigger basta con hacer:

```sql
drop trigger <nombre>
```
$\space$
### 2.1.Ejemplo 1: control del salario
Se puede controlar el salario mediante una restricción o una aserción. Sin embargo, los triggers permiten más posibilidades.

```sql
-- Transparente para el usuario
create trigger t_emp_salpos_air 
after insert on emp  -- debe ser after
referencing new row as nova
for each row
when (nova.sal <= 0)
delete from emp
where empno = nova.empno;
```

```sql
-- Generar una excepción
create trigger t_emp_salpos_bir
before insert on emp -- sirven before y after
referencing new row as nova
for each row
when (nova.sal <=0)
signal sqlstate '99001', 'salario inválido';
```

Para actualizar:

```sql
create trigger t_emp_salpos_aur
after update of sal on emp  -- debe ser after
referencing new row as nova
old row as vella
for each row
when (nova.sal <=0)
update emp set sal = vella.sal
where empno = nova.empno;  -- poco eficiente, mejor usar set

-- Con set
create trigger t_emp_salpos_bur
before update of sal on emp  -- debe ser before
referencing new row as nova
old row as vella
for each row
when (nova.sal <=0)  -- intercepta el valor
set nova.sal = vella.sal;
```
$\space$
### 2.2.Ejemplo 2: Generar un ID subrogado
Se puede usar un trigger con una secuencia. Al hacerlo con `set` es importante que sea de tipo `before`. 

```sql
create sequence seq_t1;

create trigger t_t1_id_bir
before insert on t1  -- debe ser before
referencing new row as nova
for each row
set nova.id = next value for seq_t1;
```
$\space$
### 2.3.Ejemplo 3: Log de modificaciones
Sería igual para insert, update y delete. Podemos hacerlo mediante una tabla llamada `log` que almacene las modificaciones.

```sql
create trigger t_emp_log_air
after insert on emp  -- sirven before y after
for each statement
insert into log(id, usuario, evento, timestamp)
values(next value for seq_log,
current_user,
'insert',
current_timestamp);
```
$\space$
## 3.Triggers instead of
Los triggers con `instead of` son un tipo especial de trigger que solo se puede usar con vistas. No permiten el uso de condiciones y ejecutan el trigger en lugar de el evento. Se suelen hacer para permitir actualizaciones en vistas.

```sql
create view vemp1 as
select deptno, count(*) as numemps
from emp
group by deptno;

delete from vemp1 
where deptno=10;  -- vista no actualizable, falla

create trigger t_vemp1_borrado_iodr
instead of delete on vemp1
referencing old row as vella
for each row
delete from emp where deptno = vella.deptno;

delete from vemp1 
where deptno=10;  -- funciona, elimina todos los empleados del departamento 10
```




