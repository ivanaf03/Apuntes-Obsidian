[[Tema 1-Catálogo]]

## 1.Estructura estándar
El estándar propone dividir el catálogo en capas.

![[catalogo.png]]

### 1.1.Esquema
Es una colección de elementos individuales, como tablas, vistas, triggers, etc. Un esquema pertenece a un solo usuario. Un usuario puede tener múltiples esquemas. 

### 1.2.Catálogo
Es un conjunto de esquemas. No puede haber dos esquemas con el mismo nombre dentro de un catálogo. Todos los catálogos contiene un esquema llamado `information.schema` que contiene información de todos los esquemas del catálogo y de sus elementos.

### 1.3.Cluster
Es un conjunto de catálogos. Cada usuario tiene un cluster, que es un conjunto de catálogos a los cuales tiene acceso. Es la capa más alta en la que un usuario puede hacer una consulta.

### 1.4.Entorno SQL
Contexto en que los datos existen y en el cuál se pueden realizar operaciones con ellos. Se puede considerar a nivel práctico una instancia del SGBD que se está ejecutando en una instalación concreta.

## 2.Almacenamiento y exposición de metadatos
Los metadatos también se almacenan en la base de datos.

### 2.1.Almacenamiento
Los metadatos se almacenan en un conjunto de tablas llamado `definition_schema`. No son accesibles por los usuarios. El estándar permite realizar diferentes implementaciones de estas tablas.

### 2.2.Exposición
Los metadatos se exponen mediante una colección de vistas en el `information_schema`. Los usuarios pueden consultarlas para ver los metadatos.

Algunas de estas vistas son:
+ **SCHEMATA:** esquemas propiedad del usuario actual.
+ **TABLES:** tablas accesibles por el usuario actual.
+ **COLUMNS:** columnas de las tablas accesibles por el usuario actual.
+ **VIEWS:** vistas accesibles por el usuario actual e información sobre las propias vistas del `information_schema`.
+ **DOMAINS:** dominios accesibles por el usuario actual.


