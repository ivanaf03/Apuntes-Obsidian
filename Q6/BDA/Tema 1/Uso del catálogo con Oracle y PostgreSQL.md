[[Tema 1-Catálogo]]

## 1.Oracle
Oracle no sigue el estándar. 

### 1.1.Elementos de una instalación
El Container Database (CDB) es una característica que permite tener varias bases de datos en una misma instalación, llamadas Pluggable Database (PDB). Cada PDB contiene su propio diccionario de datos y conjunto de archivos, pero todas mantienen la misma estructura de sistema de archivos y procesos.

Esto trajo los conceptos de contenedores y usuarios comunes. Los contenedores son espacios lógicos donde residen las PDB y el diccionario de datos compartido. A pesar de añadir usuarios comunes, lo normal es que cada base de datos tenga sus propios usuarios. 

Cada usuario tiene un único esquema con el propio nombre de usuario. Los esquemas contienen objetos como tablas, índices, sinónimos, etc.

El nombre de un elemento tiene el formato `USER.OBJECT`. Por ejemplo:

```sql
select * from scott.emp;
```

### 1.2.Vistas del catálogo
Podemos usar las vistas del catálogo para ver que objetos hay en la BD:
+ **USER_\<OBJECT>:** objetos creados por el usuario actual.
+ **ALL_\<OBJECT>:** objetos a los cuales el usuario actual tiene privilegios de acceso.
+ **DBA_\<OBJECT>:** todos los objetos de la BD. Solo pueden ser consultadas por los DBA, los usuarios con el rol de administrador.
+ **CDB_\<OBJECT>:** todos los objetos de todas las PDB si se accede desde el contenedor raíz CDB$ROOT. Solo pueden ser consultadas por los DBA.

#### 1.2.1.Que objetos podemos utilizar?
Oracle permite, entre otros, consultar las vistas de:
+ Objects (todos los objetos)
+ Tables
+ Views
+ Indexes
+ Constraints
+ Synonyms

#### 1.2.2.Otras vistas
Otras vistas interesante que podemos consultar en el catálogo son:
+ **DICTIONARY o DICT:** descripción breve de las vistas del catálogo.
+ **OBJ:** sinónimo de `USER_OBJECTS`.
+ **TABS:** sinónimo de `USER_TABLES`.
+ **COLS:** sinónimo de `USER_TAB_COLUMNS`. Son las columnas de las tablas del usuario.
+ **TAB:** tablas y vistas del usuario.
+ **USER_CONS_COLUMNS:** columnas implicadas en las restricciones de las tablas.

## 2.PostgreSQL
PostgreSQL sigue el estándar, pero varia un poco la nomenclatura de las cosas.

### 2.1.Nomenclatura

| **Estándar** | **PostgreSQL** |
| ------------ | -------------- |
| Esquema      | Schema         |
| Catálogo     | Database       |
| Cluster      | -              |
| Entorno SQL  | Cluster        |

### 2.2.Elementos de una instalación
Los usuarios pueden crear múltiples bases de datos y una base de datos pertenece a solo un usuario. Se puede acceder a bases de datos de otros usuarios, a lo que equivaldría el cluster en el estándar, pero no tiene un nombre concreto el conjunto.

Las bases de datos están formadas por esquemas. Un usuario puede crear varios esquemas en una sola base de datos. Cada base de datos contiene el `information_schema` y el `pg_catalog`.

### 2.3.Ejemplo de uso del catálogo

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

#### 2.3.1.Uso de information_schema

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

#### 2.3.2.Uso de pg_catalog

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
