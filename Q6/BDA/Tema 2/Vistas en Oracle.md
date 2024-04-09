[[Tema 2-Vistas]]

# Creación
```sql
create [or replace] view nombre_vista [<lista_atributos>]
as <sentencia_select>
[with check option]
```

+ [i] **Consideraciones:**
+ Sigue el estándar.
+ Permite `order by` en el `select`.
+ Siempre hace en cascada `with check option`.
+ Permite restricciones limitadas para las vistas.
+ Permite `replace` para modificar la definición de una vista.

# Eliminación
```sql
drop view nombre_vista [cascade constraints];
```

+ [i] **Consideraciones:**
+ Borra la vista y marca como inválidas las definidas sobre ella.
+ Permite `cascade constraints`.

# Actualización
## Alter
```sql
alter view nombre_vista compile;
```

+ [i] **Consideraciones:**
+ Permite volver a marcar una vista como válida.
+ No sirve para modificar la consulta asociada a la vista.

## Actualización a través de vistas
+ [<] **Variantes del estándar:**
+ Permite insertar filas cuando la vista tiene expresiones.
+ Es actualizable aunque tenga un `where` con una subconsulta a la misma tabla del `from`.
+ Permite actualizar vistas definidas sobre `join` en la tabla preservada por clave.

### Ejemplos
```sql
insert into emp10_sal values(1234, 'pepe', null);
-- Incorrecto: Intentando insertar en una columna virtual 
```

```sql
insert into emp10_sal(empno, ename) values(1234, 'pepe');
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
from emp e 
join dept d on e.deptno = d.deptno;

insert into empdep(empno, ename, sal, deptno) values (1234, 'pepe', 1000, 10);
```
