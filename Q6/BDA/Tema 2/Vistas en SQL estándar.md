[[Tema 2-Vistas]]

## 1.Definición en el estándar
### 1.1.Creación
Según el estándar se puede crear una vista partir de una secuencia `select` con este formato:

```sql
create view vista [(<atributos>)]
as <sentencia select>
[<with [cascaded | local] check option>]
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
+ No se pueden actualizar vistas ni añadir nuevas filas en vistas que usen expresiones, por ejemplo, cálculos o funciones.
+ A partir de SQL 1999 si la vista está definida sobre un `join` se pueden actualizar los atributos preservados por clave primaria.

#### 1.3.2.Check option y tuplas migratorias
Las tuplas migratorias son filas que no cumplen las condiciones de la vista al insertarlas, por tanto no se ven en la vista pero que sí se insertan en la tabla base.

```sql
insert into emp10(empno, ename, deptno)
values(1234, 'PEPE', 20);
--Se inserta a Pepe en la tabla base, pero no aparece en la vista porque es del departamento 20
```

También puede ocurrir que desaparezcan filas de la vista por culpa de modificaciones.

```sql
update emp10
set deptno=20
where ename='CLARK';
--Ahora no se ve a Clark en la vista porque se ha cambiado su departamento en la tabla base
```

Esto se puede evitar con `with check option`. Esta condición actúa de dos formas:
+ **Local:** comprueba la condición de la propia vista:

```sql
create view clerks10loc
as select empno, ename, job, deptno
from emp10
where job='CLERK'
with local check option;

insert into clerks10loc
values(1234, 'PEPE', 'MANAGER', 10); 
--No se inserta porque el trabajo no es 'CLERK'

insert into clerks10loc
values(1234, 'PEPE', 'CLERK', 20);
--Se inserta igual
```

+ **Cascaded:** es la acción por defecto, comprueba la condición de la vista y de todas en las que está definida:

```sql
create view clerks10casc
as select empno, ename, job, deptno
from emp10
where job='CLERK'
with cascaded check option;

insert into clerks10casc
values(1234, 'PEPE', 'MANAGER', 10); 
--No se inserta porque el trabajo no es 'CLERK'

insert into clerks10casc
values(1234, 'PEPE', 'CLERK', 20);
-- No se inserta porque el departamento no es el 10
```

## 2.Ventajas e inconvenientes
### 2.1.Ventajas del uso de vistas
Usar vistas permite:
+ [p] Definir diferentes esquemas externos.
+ [p] Conseguir independencia lógica.
+ [p] Mejora la seguridad, por ejemplo, ocultando datos.
+ [p] Facilitar consultas complejas.
+ [p] Establecer condiciones de integridad de datos con `check option`.
+ [p] Tener datos siempre actualizados con respecto a las tablas base. 

### 2.2.Inconvenientes del uso de vistas
A veces el uso de vistas puede resultar un problema:
+ [c] No siempre se pueden actualizar los datos a través de las vistas.
+ [c] No aumentan el rendimiento de las consultas, el rendimiento es el mismo. Al lanzar una consulta se hace SQL rewriting.