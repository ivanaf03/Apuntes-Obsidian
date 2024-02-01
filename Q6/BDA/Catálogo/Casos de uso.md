[[Bases de datos avanzadas]]

## Oracle
Oracle no sigue el estándar. 

Una instalación de Oracle tiene los siguientes elementos:
+ Una única base de datos (versión 11) o varias, el `Container Database` (versión 12). Podemos añadir `Pluggable Database` desde esta última versión.
+ Cada base de datos tiene usuario propios.
+ Cada usuario tiene un único esquema (mismo nombre).
+ Cada esquema tiene elementos, denominados `objects`: tablas, vistas, índices...

El nombre de un elemento es el nombre de usuario o esquema y el del objeto unidos por un punto. Por ejemplo, `SCOTT.EMP`.

Para cada tipo de objeto existen vistas. Tiene la siguiente nomenclatura:
+ **USER_\<objeto>:** objetos creados por el usuario.
+ **ALL_\<objeto>:** objetos a los que el usuario tiene permiso.
+ **DBA_\<objeto>:** todos los objetos.
+ **CDB_\<objeto>:** todos los objetos de todas las PDBs si se consulta `CDB$ROOT`.

El valor \<objeto> puede ser:
+ OBJECTS
+ TABLES
+ VIEWS
+ INDEXES
+ CONSTRAINTS
+ SYNONYMS

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

Se caracteriza por:
+ Un usuario puede crear múltiples bases de datos y una base de datos es de solo un usuario.
+ Un usuario puede acceder a bases de datos de otros usuarios, pero no existe como tal un clúster.
+ Dentro de una BD puede haber varios esquemas. Un usuario puede crear varios esquemas y un esquema es de un solo usuario.
+ Cada base de datos contiene el `information_schema`.

### Ejemplos
```sql
-- Creación de esquemas
CREATE SCHEMA abd;
CREATE SCHEMA mai;
CREATE SCHEMA bda;

-- Definición de la tabla en el esquema 'abd'
CREATE TABLE abd.estudiante (
    dni VARCHAR(9),
    apellidos VARCHAR(80) NOT NULL,
    nombre VARCHAR(40) NOT NULL,
    login VARCHAR(50) NOT NULL,
    CONSTRAINT pk_estudiante PRIMARY KEY (dni),
    CONSTRAINT u_login_est UNIQUE (login)
);

-- Definición de la tabla en el esquema 'mai'
CREATE TABLE mai.estudiante (
    dni VARCHAR(9),
    apellidos VARCHAR(80) NOT NULL,
    nombre VARCHAR(40) NOT NULL,
    login VARCHAR(50) NOT NULL,
    CONSTRAINT pk_estudiante PRIMARY KEY (dni),
    CONSTRAINT u_login_est UNIQUE (login)
);

-- Definición de la tabla en el esquema 'bda'
CREATE TABLE bda.estudiante (
    dni VARCHAR(9),
    apellidos VARCHAR(80) NOT NULL,
    nombre VARCHAR(40) NOT NULL,
    login VARCHAR(50) NOT NULL,
    mencion VARCHAR(3) NOT NULL,
    CONSTRAINT pk_estudiante PRIMARY KEY (dni),
    CONSTRAINT u_login_est UNIQUE (login),
    CONSTRAINT ch_mencion CHECK (mencion IN ('ES', 'SI'))
);
```

```sql
select table_schema, table_name, table_type 
from information_schema.tables
where table_schema in (’abd’,’bda’,’mai’);
```

| table_schema | table_name  | table_type |
|--------------|-------------|------------|
| abd          | estudiante  | BASE TABLE |
| bda          | estudiante  | BASE TABLE |
| mai          | estudiante  | BASE TABLE |
```sql
select schemaname, tablename 
from pg_catalog.pg_tables
where schemaname in (’abd’,’bda’,’mai’);
```

| schemaname | tablename  |
|------------|------------|
| abd        | estudiante |
| bda        | estudiante |
| mai        | estudiante |
