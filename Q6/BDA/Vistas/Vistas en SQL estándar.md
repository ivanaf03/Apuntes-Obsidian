[[Vistas]]

## Definición
```
CREATE VIEW nombre <lista_atributos>
AS <sentencia_SELECT>
<check_option>
```

El esquema o lista de atributos debe ser válido. El `SELECT *` se expande a toda la lista de atributos.

### Ejemplo 1 de clase
```sql
select view v
as select * from dept;
```

```sql
alter table dept add phone char(15);
```

La vista no añade el campo `phone`.

### Ejemplo 2 de clase
```sql
create view v1 as
select * from emp natural join dept;

create view v2 as 
select * from emp e join dept d on e.deptno=e.deptno;
```

La primera vista no cumple los requisitos de integridad referencial.

### Ejemplos
```sql
CREATE VIEW emp10 AS
SELECT *
FROM emp
WHERE deptno = 10;

CREATE VIEW emp10_sal AS
SELECT empno, ename, sal + COALESCE(comm, 0) AS sal_total
FROM emp10;

CREATE VIEW resumedep (deptno, nomedep, numemps, salmedio) AS
SELECT deptno, dname, COUNT(*), AVG(sal)
FROM emp
NATURAL JOIN dept
GROUP BY deptno, dname;

```

## Eliminación
```sql
drop view nombre_vista <restrict | cascade>;
```

+ **Restrict:** Por defecto, no borra vistas dependientes.
+ **Cascade:** Borra las vistas dependientes.

### Ejemplos
```sql
drop view emp10; -- falla: emp10_sal depende de emp10
drop view emp10 cascade; -- elimina emp10_sal
drop view resumedep restrict; -- Ok
```

## Actualización
No existe alter view. Para actualizar una vista el SGBD debe llegar de una fila de la vista a una fila de la tabla base.

Según la norma una vista no será actualizable si:
+ No hay eliminación de duplicados ni agrupamientos (no se usa `SELECT DISTINCT` ni `GROUP BY` o `HAVING`).
+ No se define la vista con `JOIN`.
+ No es el resultado de una `UNION`, `INTERSECT` o `EXCEPT`.
+ Si tiene un `WHERE` con una subconsulta, no puede ser a la misma tabla del `FROM`.
+ Se deben satisfacer las restricciones de la tabla base.
+ Si la vista utiliza expresiones no permitirá actualizar la expresión ni insertar nuevas filas.

### Tupla migratoria
Consiste en insertar una fila que no cumple las condiciones de la vista. Se inserta en la tabla base y no se ve en la vista. 
```sql
insert into emp10(empno, ename, deptno)
values(1234, 'PEPE', 20);

update emp10
set deptno=20 
where ename='CLARK';
```

Se puede evitar con `check option`:
```sql
create view emp10check
as select * from emp
where deptno=10 
with check option; 

insert into emp10check(empno, ename, deptno)
values(1234, ’PEPE’, 20); --Falla
```

Puede ser:
+ **Local:** 
+ **Cascaded:** 

```sql
create view clerks10loc
as select empno, ename, job, deptno
from emp10 where job='CLERK'
with LOCAL check option;

insert into clerks10loc
values(1234, ’PEPE’, ’MANAGER’, 10); -- No inserta

insert into clerks10loc 
values(1234, ’PEPE’, ’CLERK’, 20); -- Inserta
```

```sql
create view clerks10loc
as select empno, ename, job, deptno
from emp10 where job='CLERK'
with CASCADED check option;

insert into clerks10loc
values(1234, 'PEPE', 'MANAGER', 10); -- No inserta

insert into clerks10loc 
values(1234, 'PEPE', 'CLERK', 20); -- No inserta
```

## Ventajas e inconvenientes
### Ventajas
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
+ Los datos siempre están actualizados.

### Inconvenientes
+ Limitaciones a la hora de actualizar los datos.
+ No aumentan la eficiencia de las consultas, se hace un `sql rewriting`.