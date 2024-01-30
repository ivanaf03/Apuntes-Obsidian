[[Bases de datos avanzadas]]

## Oracle
Oracle no sigue el estándar. 

Una instalación de Oracle tiene los siguientes elementos:
+ Una única base de datos (versión 11) o varias, el Container Database (versión 12).
+ Cada base de datos tiene usuario propios.
+ Cada usuario tiene un único esquema (mismo nombre).
+ Cada esquema tiene elementos, denominados objects: tablas, vistas, índices...

Para cada tipo de objeto existen vistas. Tiene la siguiente nomenclatura:
+ **USER_\<objeto>:** 
+ **ALL_\<objeto>:** 
+ **DBA_\<objeto>:** 
+ **CDB_\<objeto>:** 

\<objeto> puede ser:
+ OBJECTS
+ TABLES
+ ...

### Sinónimos
Un sinónimo es un alias para referenciar otro elemento. Por ejemplo, cuando hacemos:
```sql
select * from emp;
```

Realmente no tenemos la tabla `emp`, pero `emp` es un sinónimo público de `docencia.emp`.

## PostgreSQL
PostgreSQL sigue el estándar, pero varía la nomenclatura:

| Estándar | PostgreSQL |
| ---- | ---- |
| Esquema | Schema |
| Catálogo | Database |
| Cluster | - |
| Entorno SQL | Cluster |

