[[Vistas]]

# ¿Qué son las vistas materializadas?
También se llaman `snapshots`. Almacenan el resultado de la consulta en disco. Las consultas son más rápidas, aunque ocupan espacio y hay que actualizar el contenido. 

Oracle permite especificar cuando materializar la vista y cómo y cuándo refrescar esos datos para mantenerlos sincronizados con las tablas base.

## Materialización
+ [<] **Tipos:**
+ *Inmediata:* cuando se define.
+ *Aplazada:* en el primer refresco.
+ *Prebuilt table:* utilizando una tabla preexistente.
$\space$
+ [<] **Modos de refresh:**
+ *Complete:* recrea la vista al completo. Puede hacerse en cualquier momento, pero es muy costoso.
+ *Fast:* incremental, actualiza solo la información nueva mediante `materialized view logs` en las tablas base. No siempre es posible.
+ *Force:* default, hace incremental y, si no puede, completo.
$\space$
+ [<] **Modos de actualización:**
+ *On commit:* durante el commit de cada transacción de las tablas base.
+ *On demand:* de forma manual.
+ *Periódicamente:* se indica una periodicidad.
+ *Never refresh:* nunca.

## Ejemplos
```sql
create materialized view mv_empdep
build immediate -- Predeterminado
refresh force -- Predeterminado
on demand -- Predeterminado
enable query rewrite
as
select *
from emp natural join dept;

create materialized view mv_emphours
build deferred
refresh complete
start with sysdate next sysdate + 1
as
select e.empno, ename, p.prono, pname, hours
from emp e
join emppro ep on e.empno=ep.empno
join pro p on ep.prono=p.prono;

select mview_name, build_mode build, refresh_method metodo_ref,
refresh_mode modo_ref, fast_refreshable, rewrite_enabled rewrite
from user_mviews;
```

# Consultas
Se pueden hacer consultas sobre vistas materializadas como si fueran tablas. Incluso se pueden añadir índices.
```sql
create index i_mv_empdep_sal
on mv_empdep(sal);

select *
from mv_empdep
where sal > 3000;
```

## Reescritura de consultas
El `query rewrite` es una característica en Oracle que permite al optimizador de consultas utilizar vistas materializadas de manera inteligente, incluso si estas vistas no están directamente referenciadas en la consulta original. 

Esto se puede activar o desactivar.
```sql
alter session set query_rewrite_enabled={true | false}
```


