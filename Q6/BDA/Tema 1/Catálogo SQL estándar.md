[[Tema 1-Catálogo]]

## 1.Estructura
El catálogo estándar se estructura en:
+ **Esquema:** colección de elementos como tablas, vistas, triggers, etc. Un usuario puede tener varios esquemas, pero un esquema está asociado a un único usuario.
+ **Catálogo:** conjunto de esquemas con diferentes nombres. Se puede accede a un elemento de la base de datos con `catálogo.esquema.elemento`. Todo catálogo contiene un esquema con información sobre todos los esquemas que contiene llamado `information.schema`.
+ **Cluster:** colección de catálogos a los que un usuario tiene acceso. Equivale a la base de datos que ve un usuario.
+ **Entorno:** contexto donde los datos existen y donde se pueden realizar operaciones sobre ellos. En la práctica esto es una instancia del SGBD.

$\space$
![[catalogo.png]]

## 2.Almacenamiento y exposición de metadatos
Los metadatos informan sobra la estructura, organización, contenido y uso de los datos. También se almacenan en la base de datos.

### 2.1.Almacenamiento
El SGBD debe almacenar los metadatos en un conjunto de tablas llamado `definition.schema` que no puede ser accedido por el SQL de los usuarios.

### 2.2.Exposición
Los datos se exponen mediante una colección de vistas denominado `information.schema`. Contiene:
+ **SCHEMATA:** esquemas del usuario actual.
+ **TABLES:** tablas persistentes del usuario actual.
+ **COLUMNS:** columnas de las tablas del usuario actual.
+ **VIEWS:** vistas del usuario actual.
+ **DOMAINS:** dominios accesibles por el usuario actual.


