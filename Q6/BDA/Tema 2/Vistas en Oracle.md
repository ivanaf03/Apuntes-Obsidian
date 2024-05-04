[[Tema 2-Vistas]]

## 1.Uso de vistas en Oracle
### 1.1.Creación
Se pueden crear vistas en Oracle de una forma muy similar al estándar:

```sql
create [or replace] view vista [(<atributos>)]
as <sentencia select>
[<with check option>]
```

#### 1.1.1.Cambios con respecto al estándar
Las vistas de Oracle se diferencian del estándar en:
+ Permiten  `order by` en la sentencia `select`.
+ Siempre se hace en cascada el `check option`.
+ Permite el uso de ciertas restricciones, como el uso de claves foráneas o primarias.
+ Se puede modificar una vista con `replace view`.

### 1.2.Borrado
Se puede borrar una vista con:

```sql
drop view vista;
```

Borra la vista y marca como inválidas todas las vistas definidas sobre ella. Permite añadir `cascade constraints` en caso de que la vista tenga restricciones.

### 1.3.Restaurar vistas
Cuando una fila se marca como inválida se puede volver a validar con:

```sql
alter view vista compile;
```

Es importante recordar que `alter` no permite modificar la vista, se debe usar `create or replace`.

## 2.Actualización a través de vistas en Oracle
Se pueden actualizar tablas a través de vistas de forma similar al estándar. Se diferencian en:
+ Permite insertar filas aunque la vista tenga expresiones si no se actúa sobre la columna con expresiones.
+ Es actualizable aunque la vista tenga un `where` con una subconsulta a la misma tabla del `from`.
+ Permite actualizar vistas definidas sobre un `join`, pero solo en la tabla preservada por clave.

### 2.1.Ejemplos

```sql
insert into emp10_sal values(1234, 'pepe', null);
-- Error: Intentando insertar en una columna virtual 

insert into emp10_sal(empno, ename) values(1234, 'pepe');
-- Inserta
```

```sql
create view empcaro as
select * 
from emp
where sal > (select avg(sal) from emp);

delete from empcaro;
```

```sql
create view empdep as
select empno, ename, sal, e.deptno, dname
from emp e join dept d on e.deptno = d.deptno;

insert into empdep(empno, ename, sal, deptno) values (1234, 'pepe', 1000, 10);
```
