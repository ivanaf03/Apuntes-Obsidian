[[Integridad]]

# 1.Oracle
Oracle no implementa dominios. Implementa las restricciones:
+ [>] Primary key
+ [>] Not null
+ [>] Unique
+ [>] Foreign key/ References
+ [>] Check 

$\space$
Permite modo aplazado.

## 1.1.Activación y comprobación
Las restricciones pueden estar en estado `enable` o `disable`. Por defecto comprueba las filas existentes, estado `validate`, pero puede indicarse que no `novalidate`.

Esto se especifica al crear o modificar las tablas.

```sql
alter table <table> modify constraint <nome_restr> { enabled | disabled } { validate | novalidate};

alter table <table> { enable | disable } constraint <nome_restr>;
```

## 1.2.Claves foráneas
Con respecto a las claves foráneas Oracle:
+ [>] No permite la cláusula `match`. Se comporta `match simple`.
+ [>] No permite  

# 2.PostgreSQL
PostgreSQL implementa dominios. Implementa las restricciones:
+ [>] Primary key
+ [>] Not null
+ [>] Unique
+ [>] Foreign key/ References
+ [>] Check
+ [>] Exclude 

$\space$
Pueden consultarse las restricciones en el catálogo en `pg_catalog.pg_constraints` y en varias vistas de `information_schema`.