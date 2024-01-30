[[Catálogo]]

## Estructura
![[catalogo.png]]

+ **Esquema:** Un usuario puede tener varios esquemas y un esquema pertenece a un usuario. Es una colección de elementos individuales como tablas, vistas, triggers, etc.
+ **Catálogo:** Conjunto de esquemas.
+ **Cluster:** Colección de catálogos.
+ **Entorno SQL:** Contexto en que los datos pueden existir y donde se pueden realizar operaciones sobre ellos.

## Almacenamiento y exposición de metadatos
El SGBD debe almacenar los metadatos en un conjunto de tablas llamado `definition.schema` que solo puede ser accedido por el SQL de los usuarios. Expone los datos en vistas:
+ **SCHEMATA:** 
+ ...

