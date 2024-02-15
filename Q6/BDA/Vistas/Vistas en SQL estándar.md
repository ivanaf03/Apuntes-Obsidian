[[Vistas]]

# Definición
```sql
create view nombre_vista [<lista_atributos>]
as <sentencia_select>
[with [cascaded | local] check option]
```

+ [i] **Consideraciones:**
+ El esquema o lista de atributos debe ser válido.
+ El `select *` se expande a toda la lista de atributos.
+ El `select` no incluye `order by`.
+ La `check_option` solo aplica si la vista es actualizable.

## Ejemplo 1
```sql
create view v
as select * from dept;
```

```sql
alter table dept
add column phone char(15);
```

La vista no añade el campo `phone`.

## Ejemplo 2
```sql
create view v1 as
select * from emp natural join dept;

create view v2 as 
select * from emp e join dept d on e.deptno=d.deptno;
```

La primera vista no cumple los requisitos de integridad referencial porque utiliza `natural join`.

## Ejemplo 3
```sql
create view emp10 as
select *
from emp
where deptno = 10;

create view emp10_sal as
select empno, ename, sal + coalesce(comm, 0) as sal_total
from emp10;

create view resumedep (deptno, nomedep, numemps, salmedio) as select deptno, dname, count(*), avg(sal)
from emp
natural join dept
group by deptno, dname;
```

# Eliminación
```sql
drop view nombre_vista [restrict | cascade];
```

+ [<] **Atributos:**
+ *Restrict:* Por defecto, no borra vistas dependientes.
+ *Cascade:* Borra las vistas dependientes y después la actual.

## Ejemplos
```sql
drop view emp10; -- falla: emp10_sal depende de emp10
drop view emp10 cascade; -- elimina emp10_sal
drop view resumedep restrict; -- elimina resumedep
```

# Actualización
No existe `alter view`. Para actualizar una vista el SGBD debe llegar de una fila de la vista a una fila de la tabla base.

+ [p] **Es actualizable:**
+ Si no hay eliminación de duplicados ni agrupamientos (no se usa `select distinct` ni `group by` o `having`).
+ Si no se define la vista con `join`.
+ Si no es el resultado de una `union`, `intersect` o `except`.
+ Si tiene un `where` con una subconsulta, no puede ser a la misma tabla del `from`.

Se deben satisfacer las restricciones de la tabla base.
```sql
create table empleados (
    id int primary key,
    nombre varchar(50) not null,
    salario decimal(10, 2)
);

create view vista_empleados as
select id, salario
from empleados;

insert into vista_empleados (id, salario) values (1, 5000.00); -- Error
```

Si la vista utiliza expresiones no permitirá actualizar la expresión ni insertar nuevas filas.
```sql
create view vista_salario_doble as
select id, nombre, salario * 2 as salario_doble
from empleados;

update vista_salario_doble
set salario_doble = salario_doble + 1000; -- Error
```

## Tupla migratoria
Ocurre al insertar una fila que no cumple las condiciones de la vista. Se inserta en la tabla base y no se ve en la vista. Se puede evitar con `check option`:

+ [<] **Atributos de check option:**
+ *Local:* comprueba solo la condición de la vista.
+ *Cascaded:* por defecto, comprueba la condición de la vista y de todas las que depende.

### Ejemplo 1
```sql
insert into emp10(empno, ename, deptno)
values(1234, 'PEPE', 20);

update emp10
set deptno=20 
where ename='CLARK';
```

```sql
create view emp10check
as select * from emp
where deptno=10 
with check option; 

insert into emp10check(empno, ename, deptno)
values(1234, 'PEPE', 20); --Falla
```

### Ejemplo 2
```sql
create view clerks10loc
as select empno, ename, job, deptno
from emp10 where job='CLERK'
with local check option;

insert into clerks10loc
values(1234, 'PEPE', 'MANAGER', 10); -- No inserta

insert into clerks10loc 
values(1234, 'PEPE', 'CLERK', 20); -- Inserta
```

```sql
create view clerks10loc
as select empno, ename, job, deptno
from emp10 where job='CLERK'
with cascaded check option;

insert into clerks10loc
values(1234, 'PEPE', 'MANAGER', 10); -- No inserta

insert into clerks10loc 
values(1234, 'PEPE', 'CLERK', 20); -- No inserta
```

## Ventajas e inconvenientes

+ [p] **Ventajas:**
+ Permiten definir esquemas externos.
+ Ayudan a conseguir independencia lógica.
+ Facilitan las consultas complejas.
```sql
select deptno, dname, avg(sal)
from emp natural join dept
group by deptno, dname
having count(*)>2;


-- Esta consulta se puede facilitar con vistas

create view ed1
as select *
from emp natural join dept;

create view ed2
as select deptno, dname, avg(sal) media, count(*) cnt
from ed1 group by deptno, dname;

select deptno, dname, media
from ed2
where cnt>2;
```
+ Permite seguridad, por ejemplo ocultando datos.
+ Permite establecer condiciones de integridad con `check option`.
+ Los datos siempre están actualizados con respecto a las tablas base.
$\space$
+ [c] **Inconvenientes:**
+ Limitaciones a la hora de actualizar los datos.
+ No aumentan la eficiencia de las consultas, se hace un `sql rewriting`.