[[Tema 5-Bases de datos activas]]
$\space$
## 1.Comparación con el estándar
Oracle incluye más tipos de eventos que los 3 del estándar. Permite que un trigger controle más de un evento mediante `or`; basta con que coincidan en tiempo de activación y granularidad. 

No usa tablas de transición, solo variables de transición. 

Las condiciones son limitadas, no admiten subconsultas. Puede omitirse el `when` si se usa `if` en la acción.

Las acciones pueden ser SQL o llamadas a procedimientos. No admiten sentencias transaccionales. Las variables de transición van precedidas de 2 puntos.
$\space$
## 2.Sintaxis y uso de triggers
Para crear un trigger:

```sql
create or replace trigger <nome_trigger>
before|after|instead of
<evento> [or <evento>...] on <tabla>
referencing [new as tupla_nova]
[old as tupla_vella]
for each row
when (<condicion_sql_simple>)
{ <bloque pl/sql> | call <procedemento(argumentos)> }
```

Para eliminar un trigger:

```sql
drop trigger <nome_trigger>
```

Para activar o desactivar triggers:

```sql
alter trigger <nome_trigger> {enable|disable}

alter table <t´aboa> {enable|disable} all triggers
```
$\space$
### 2.1.Consultas en el catálogo
Podemos consultar las tablas `all_triggers` y `user_triggers`. Por ejemplo:

```sql
desc user_triggers
```

![[triggers catalogo.png]]
$\space$
### 2.2.Ejemplos
Veamos algunos ejemplos de uso de triggers.
$\space$
#### 2.2.1.Control de salario
Se hace de forma similar al estándar. Se cambia `referencing` por `new`. 

Puede lanzar un error al insertar:

```sql
create or replace trigger t_emp_salpos_bir
before insert on emp
for each row
when (new.sal <= 0)
begin
raise_application_error(-20001,'Salario '||:new.sal||' inválido');
end;
/
-- Lanza un error si se intenta insertar, funciona
```

Puede generar tablas mutantes:

```sql
create or replace trigger t_emp_salpos_air
after insert on emp
for each row
when (new.sal <= 0)
begin
delete from emp
where empno = :new.empno;
end;
-- Se crea el trigger, pero no funciona como en el estándar. En su lugar genera una tabla mutante. No es posible acceder a la tabla controlada por el trigger (ni modificaciones ni select)
```

Podemos dejar el salario anterior combinando dos triggers. 

```sql
create or replace trigger t_emp_salpos_biur
before insert or update on emp
for each row
when (new.sal <= 0)
begin
if updating then
:new.sal := :old.sal;
else -- inserting
raise_application_error(-20001,'Salario '||:new.sal||' inválido');
end if;
end;
```
$\space$
#### 2.2.2.Generación de un ID subrogado
Es similar al estándar.

```sql
create table t1(
id number(3) constraint pk_t1 primary key,
a varchar(5));
create sequence seq_t1;
create trigger t_t1_id_bir
before insert on t1
referencing new as nova -- poderíamos omitirlo y usar new
for each row
begin
:nova.id := seq_t1.nextval;
end;

insert into t1(a) values ('fila1');
insert into t1(a) values ('fila2');

select * from t1;
-- 1 fila1
-- 2 fila2

```
$\space$
#### 2.2.3.Log de modificaciones
Permite hacerlo para los 3 eventos a la vez:

```sql
create or replace trigger t_emp_log_air
after insert or update or delete on emp  -- sirven before y after
declare
    op varchar2(20);
begin
    if inserting then
        op := 'insert';
    elsif updating then
        op := 'update';
    else -- deleting
        op := 'delete';
    end if;
    
    insert into log(id, usuario, evento, timestamp)
    values(seq_log.nextval, user, op, current_timestamp);
end;
```
$\space$
## 3.Trigger instead of
Es muy similar también al estándar. Permite hacer que las vistas sean actualizables, cambia la forma de actualiza en las que eran actualizables, etc.
$\space$
### 3.1.Ejemplo

```sql
create view empdep as
select * from emp natural join dept;
-- no permite la inserción: vista con join no actualizable

insert into empdep
values(10, 7001, 'PARKER', 'CLERK', 7782, '12/01/2015',
1800, NULL, 'VENTAS', 'LONDON');

-- error en línea 1:
-- ora-01779: no se puede modificar una columna que se corresponde con una tabla no preservada por clave
```

Hay que hacer la actualización de forma manual, por ejemplo, si el departamento existe se actualizan el nombre y la localidad. Si no existe, se crea. Si el empleado ya existe, se genera una excepción. Si no, se inserta.

```sql
create or replace trigger t_empdep_insert_ioir
instead of insert on empdep
for each row
declare
    n number;
begin
    select count(*) into n from emp
    where empno = :new.empno;
    
    if n > 0 then
        raise_application_error(-20036, 'Empregado existente');
    end if;
    
    update dept set dname = :new.dname, loc = :new.loc
    where deptno = :new.deptno;
    
    if sql%notfound then -- no existía: inserto
        insert into dept(deptno, dname, loc) values(:new.deptno, :new.dname, :new.loc);
    end if;
    
    insert into emp(empno, ename, job, mgr, hiredate, sal, comm, deptno)
    values(:new.empno, :new.ename, :new.job, :new.mgr,
           :new.hiredate, :new.sal, :new.comm, :new.deptno);
end;

```

```sql
select * from dept where deptno = 10;
-- Resultado:
-- 10 ACCOUNTING NEW YORK

select * from emp where empno = 7001;
-- Resultado:
-- No hay filas

insert into empdep
values(10, 7001, 'PARKER', 'CLERK', 7782, '12/01/2015',
1800, NULL, 'VENTAS', 'LONDON');
-- Resultado:
-- 1 fila creada

select * from dept where deptno = 10;
-- Resultado:
-- 10 VENTAS LONDON

select * from emp where empno = 7001;
-- Resultado:
-- 7001 PARKER CLERK 7782 12/01/15 1800 10
```