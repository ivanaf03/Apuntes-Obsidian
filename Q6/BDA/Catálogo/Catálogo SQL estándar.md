[[Catálogo]]

## Estructura
![[catalogo.png]]
+ **Esquema:** un usuario puede tener varios esquemas y un esquema pertenece a un usuario. Es una colección de elementos individuales como tablas, vistas, triggers, etc.
+ **Catálogo:** conjunto de esquemas con nombres únicos. Los elementos de la base de datos son accesibles con `catálogo.esquema.elemento`. Todo catálogo debe contener un esquema `information_schema` que contiene la información de todos los esquemas.
+ **Cluster:** colección de catálogos. Cada usuario tiene uno asociado. Para un usuario podría decirse que es su base de datos.
+ **Entorno SQL:** contexto en que los datos pueden existir y donde se pueden realizar operaciones sobre ellos. Es una instancia del SGBD que se está ejecutando en una instalación concreta.

## Almacenamiento y exposición de metadatos
El SGBD debe almacenar los metadatos en un conjunto de tablas llamado `definition.schema` que no puede ser accedido por el SQL de los usuarios. Expone los datos en vistas:
+ **SCHEMATA:** esquemas del usuario actual.
+ **TABLES:** tablas persistentes del usuario actual.
+ **COLUMNS:** columnas de las tablas del usuario actual.
+ **VIEWS:** vistas del usuario actual.
+ **DOMAINS:** dominios accesibles por el usuario actual.



