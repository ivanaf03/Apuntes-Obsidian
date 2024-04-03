[[Tema 1-Catálogo]]

## 1.Oracle
Oracle no sigue el estándar. 

### 1.1.Elementos de una instalación
Una instalación contiene:
+ Una única base de datos (versión 11) o varias, el `Container Database` (versión 12). Podemos añadir `Pluggable Database` desde esta última versión.
+ Usuarios propios.
+ Un esquema por usuario con el mismo nombre.
+ Objetos dentro de un esquema, como tablas, vistas, índices, etc. Se nombran como el nombre de usuario o esquema y el del objeto unidos por un punto. Por ejemplo, `scott.emp`. 

$\space$
Para cada tipo de objeto existen las vistas:
 + **user_\<objeto>:** objetos creados por el usuario.
+ **all_\<objeto>:** objetos a los que el usuario tiene acceso.
+ **DBA_\<objeto>:** todos los objetos. Solo pueden ser accedidas por los usuarios con rol DBA.
+ **CDB_:** todos los objetos de todas las PDB si se consulta desde el `CDB$ROOT`. Requiere también rol de DBA.

$\space$
Los objetos de Oracle son:
+ objects
+ tables
+ views
+ indexes
+ constraints
+ synonyms

## 2.PostgreSQL
PostgreSQL sigue el estándar, pero cambia la nomenclatura.

### 2.1.Nomenclatura

| **Estándar** | **PostgreSQL** |
| ------------ | -------------- |
| Esquema      | Schema         |
| Catálogo     | Database       |
| Cluster      | -              |
| Entorno SQL  | Cluster        |

### 2.2.Elementos de una instalación
En una instalación:
+ Un usuario puede crear múltiples bases de datos y una base de datos es de un único usuario.
+ Un usuario puede acceder a bases de datos de otros usuarios, pero no existe como tal un clúster.
+ Dentro de una BD puede haber varios esquemas. Un usuario puede crear varios esquemas y un esquema es de un único usuario.
+ Cada base de datos contiene el `information_schema` y el `pg_catalog`. Este último es una característica de PostgreSQL que contiene metadatos.

### 2.3.Ejemplos

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

#### 2.3.1.Ejemplo 1

```sql
select table_schema, table_name, table_type 
from information_schema.tables
where table_schema in ('abd','bda','mai');
```

| **table_schema** | **table_name**  | **table_type** |
|--------------|-------------|------------|
| abd          | estudiante  | BASE TABLE |
| bda          | estudiante  | BASE TABLE |
| mai          | estudiante  | BASE TABLE |
#### 2.3.2.Ejemplo 2
Consulta propia de PostgreSQL utilizando `pg_catalog`:

```sql
select schemaname, tablename 
from pg_catalog.pg_tables
where schemaname in ('abd','bda','mai');
```

| **schemaname** | **tablename**  |
|------------|------------|
| abd        | estudiante |
| bda        | estudiante |
| mai        | estudiante |
