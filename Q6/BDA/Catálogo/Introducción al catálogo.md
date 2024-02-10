[[Catálogo]]

# Sistemas de información
Un sistema de información es el conjunto de tecnologías, procesos, aplicaciones de negocios y software disponibles para las personas dentro de una organización.

Antes estaban compuestos por ficheros y programas que los manejaban. La estructura y descripción de los datos estaba en el propio código de los programas que los manejaban.

+ [c] **Contras:**
+ Los programas podían contener información incompatible entre ellos.
+ Faltaba documentación sobre los datos, permisos de acceso a estos, procesos que los usaban, etc.

Esta metodología era poco útil y no era mantenible.
+ [I] **Surgen:**
+ *Diccionario de datos:* lista organizada de los datos que se manejarán en el sistema, junto con sus definiciones, características y relaciones.
+ *Catálogo:* conjunto de tablas y vistas especiales que contienen información sobre la estructura y el contenido de la base de datos. Almacena metadatos sobre los objetos e la base de datos.

## Diccionario de datos
Un Diccionario de Datos (DD) es un repositorio centralizado de información que almacena metadatos, es decir, datos sobre los propios datos. Este contiene detalles sobre los datos, como su significado, tipos de datos, formatos, tamaños, restricciones, entre otros aspectos. Además, puede incluir información sobre otros elementos relacionados, como los programas que utilizan esos datos o los usuarios que tienen acceso a ellos.

La gestión de la información se realiza de manera centralizada, lo que significa que puede ser consultado y modificado por usuarios con los permisos adecuados. Esto mejora la autenticidad de la información y facilita la comunicación entre los usuarios.

+ [<] **Sirve para:**
+ Documentar el modelo de datos, incluyendo requisitos, especificaciones y diseño.
+ Generar informes sobre cualquier elemento del modelo de datos, incluidos los elementos relacionados.
+ Analizar el impacto de un cambio en el modelo de datos, como cambios en los tipos de datos o la inclusión de nuevos elementos.
+ Generar automáticamente la estructura de la BBDD.
+ Generar automáticamente la definición de datos en lenguajes de programación que acceden a esos datos, como clases Java.

## Catálogo del sistema
Es un conjunto de tablas que almacenan metadatos sobre la base de datos y los exponen de forma amigable. Se suelen llamar `tablas o vistas del sistema` para diferenciarlas de las `tablas o vistas de usuario`.

Es creado y utilizado por el SGBD y es de solo lectura para los usuarios. Los usuarios hacen modificaciones en el catálogo al realizar `operaciones DDL`.