[[Catálogo]]

## Metadatos
Un sistema de información suele plasmar conocimiento sobre un dominio. Antes estaban formados por ficheros y programas que los manejan. La estructura y la descripción de los datos estaba en el propio código. Esta metodología hacía que varios programas pudieran tener información incompatible y no había documentación sobre los usuarios, permisos...

Por esto aparecieron:
+ Diccionario de datos
+ Catálogo

### Diccionario de datos
Es un repositorio de información que almacena metadatos. Incluye información sobre los datos, como tamaño, restricciones, usuarios autorizados, etc.

Almacenan la información de forma centralizada, lo que mejora la autenticidad de la información y la comunicación entre usuarios.

Un DD permite:
+ Documentar el modelo.
+ Generar informes sobre los elementos del modelo.
+ Analizar el impacto de los cambios de un modelo de datos.
+ Generar la estructura de la base de datos.
+ Generar la definición de datos en lenguajes de programación que accedan a ellos.

### Catálogo del sistema
Es un conjunto de tablas que almacenan metadatos sobre la base de datos y los exponen de forma amigable. Se suelen llamar `tablas o vistas del sistema`.

Es creado por el SGBD y es de solo lectura para los usuarios. Los usuario hacen modificaciones en el catálogo, por ejemplo, creando una tabla o haciendo otras operaciones DDL.

El SGBD utiliza el catálogo continuamente para realizar sus funciones. Es vital para el funcionamiento del sistema.



