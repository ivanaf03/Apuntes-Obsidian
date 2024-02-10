[[Catálogo]]

# Estructura
![[catalogo.png]]
+ [<] **Partes:** 
+ *Esquema:* un usuario puede tener varios esquemas y un esquema pertenece a un único usuario. Es una colección de elementos individuales como tablas, vistas, triggers, etc.
+ *Catálogo:* conjunto de esquemas con nombres únicos. Los elementos de la base de datos son accesibles mediante `catálogo.esquema.elemento`. Todo catálogo debe contener un esquema `information_schema` que contiene la información de todos los esquemas de dentro del catálogo.
+ *Cluster:* colección de catálogos. Cada usuario tiene uno asociado. Para un usuario podría decirse que es su base de datos, puesto  que es el máximo ámbito en el que se puede ejecutar una consulta SQL.
+ *Entorno SQL:* contexto en que los datos pueden existir y donde se pueden realizar operaciones sobre ellos. Es una instancia del SGBD que se está ejecutando en una instalación concreta.

# Almacenamiento y exposición de metadatos
## Almacenamiento
El SGBD debe almacenar los metadatos en un conjunto de tablas llamado `definition.schema` que no puede ser accedido por el SQL de los usuarios.

## Exposición
Los datos se exponen mediante una colección de vistas denominado `information.schema`.
+ [<] **Contiene las vistas:** 
+ *SCHEMATA:* esquemas del usuario actual.
+ *TABLES:* tablas persistentes del usuario actual.
+ *COLUMNS:* columnas de las tablas del usuario actual.
+ *VIEWS:* vistas del usuario actual.
+ *DOMAINS:* dominios accesibles por el usuario actual.



