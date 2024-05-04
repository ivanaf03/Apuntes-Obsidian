[[Tema 2-Vistas]]

## 1.Qué son las vistas materializadas?
Una vista materializada es una copia física de los datos de una vista en una base de datos. Permite Hacer consultas más rápidas, pero ocupan espacio en disco y hay que mantenerlo actualizado.

Oracle permite especificar cuando materializar la vista y y como y cuando actualizar los datos para que estén sincronizados con las tablas base.

### 1.1.Materialización
La materialización de una vista puede ser:
+ **Inmediata:** se materializa al definir la vista.
+ **Aplazada:** la consulta se materializa la primera vez que se actualiza.
+ **On prebuilt table:** la vista utiliza una tabla ya existente de la base de datos. Comparte el segmento de datos con la tabla.

### 1.2.Modos de refresco
Una vista materializada actualiza los datos de varias formas:
+ **Complete:** recrea la vista completamente. Puede hacerse en cualquier momento, pero es muy costoso computacionalmente.
+ **Fast:** actualiza solo la nueva información mediante `materialized view logs`. Estos son unos objetos que funcionan como unos registros que actualizan la vista cada vez que se modifique la tabla base. No siempre se pueden usar.
+ **Force:** el el modo por defecto. Actúa siempre en modo fast si es posible. Sino, hace refrescos completos.

### 1.3.Periodos de actualización
Se pueden actualizar los datos:
+ **On commit:** durante el commit de cada transacción de las tablas base. No se puede hacer siempre.
+ **On demand:** de forma manual donde se necesite.
+ **Periódicamente:** se indica la periodicidad del refresco.
+ **Nunca:** nunca se actualizan.

### 1.4.Ejemplos

```sql
create materialized view mv_empddep
build inmediate  -- Predeterminado
refresh force  -- Predeterminado
on demand  -- Predeterminado
enable query rewrite
as 
select * from emp natural join dept;

create materialized view mv_emphours
build defered
refresh complete
start with sysdate next suysdate+1
as
select e.empno, ename, p.prono, pname, hours
from emp e
join emppro ep on e.empno=ep.empno
join pro p on ep.prono=p.prono;
```

```sql
select mview_name, build_mode build, refresh_method metodo_ref,
refresh_mode modo_ref, fast_refreshable, rewrite_enabled rewrite
from user_mviews;
```

| **MVIEW_NAME** | **BUILD** | **METODO_REF** | **MODO_REF** | **FAST_REFRESHABLE** | **REWRITE** |
| -------------- | --------- | -------------- | ------------ | -------------------- | ----------- |
| MV_EMPDEP      | IMMEDIATE | FORCE          | DEMAND       | NO                   | Y           |
| MV_EMPHOURS    | DEFERRED  | COMPLETE       | DEMAND       | NO                   | N           |

## 2.Consultas a vistas materializadas
Se pueden hacer consultas a las vistas materializadas como si fueran tablas. Incluso se pueden añadir índices para que sean más eficientes algunas consultas.

```sql
create index i_mv_empdep_sal
on mv_empdep(sal);

select *
from mv_empdep
where sal > 3000;
```

### 2.1.Reescritura de consultas
El `query rewrite` es una característica de Oracle que permite al optimizador trabajar de forma inteligente con las vistas materializadas aunque no estén en la consulta indicada. Se hace cuando la vista materializada o parte de ella coincide con lo pedido en la consulta.

Se puede activar y desactivar con:

```sql
alter session set query_rewrite_enabled={true|false}
```
