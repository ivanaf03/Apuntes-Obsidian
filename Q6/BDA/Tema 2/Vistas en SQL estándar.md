[[Tema 2-Vistas]]

## 1.Definición en el estándar
### 1.1.Creación
Según el estándar se puede crear una vista partir de una secuencia `select` con este formato:
```sql
create view vista [(<atributos>)]
as <sentencia select>
[<check option>]
```

#### 1.1.1.Ejemplos

```sql
--Vista de los empleados del departamento 10
create view emp10 
as select *
from emp
where deptno=10;

--Vista del sueldo basada en la vista anterior
create view emp10_sal
as select empno, ename, sal+coalesce(comm, 0) as sal_total
from emp10;

--Para cada departamento, vista del número de empleados y del sueldo medio
create view resumedep(deptno, nomedep, numemps, salmedio)
as select deptno, dname, count(*), avg(sal)
from emp natural join dept
group by deptno, dname;
```

### 1.2.Borrado
Según el estándar podemos usar `drop view` para eliminar una vista.

```sql
drop view vista [restrict | cascade]
```

#### 1.2.1.Parámetros de drop view
Se puede borrar una vista de dos formas:
+ **Restrict:** es la acción por defecto, no elimina las vistas dependientes y falla si hay vistas dependientes.
+ **Cascade:** elimina las vistas dependientes y después la actual.

#### 1.2.2.Ejemplos

```sql
--Borrado erróneo porque emp10_sal depende de emp_10
drop view emp10;

--Borrado de emp10_sal y emp10
drop view emp10 cascade;

--Borrado de resumedep
drop view resumedep restrict;
```

### 1.3.Actualización
No existe `alter view`. Para modificar una vista debemos hacer un borrado y crearla de nuevo.

#### 1.3.1.Normas
Una vista es actualizable si cuando actualizamos datos de la vista el SGBD es capaz de rastrear a que fila corresponde la actualización, es decir, tiene que corresponderse con una única fila.

Formalmente, debe cumplir:
+ No se usa `select distinct` ni `group by`.
+ No hay más de una tabla en el `from`.
+ La consulta no viene de uniones, intersecciones o excepciones.
+ No puede tener una subconsulta a su propia tabla en el `where`.
+ Deben cumplirse las restricciones de la tabla base, teniendo cuidado con los `not null` sobre todo.
+ 



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