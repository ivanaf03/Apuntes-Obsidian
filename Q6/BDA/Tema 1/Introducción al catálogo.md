[[Tema 1-Catálogo]]

## 1.Sistemas de información
Un sistema de información es el conjunto de tecnologías, procesos, aplicaciones de negocios y software disponibles para las personas dentro de una organización.

Antes estaban compuestos por ficheros y programas que los manejaban. La estructura y descripción de los datos estaba en el propio código de los programas que los manejaban.

### 1.1.Inconvenientes
Si se siguiera utilizando esta metodología:
+ [c] Los programas podían contener información incompatible entre ellos.
+ [c] Faltaba documentación sobre los datos, permisos de acceso a estos, procesos que los usaban, etc.

### 1.2.Soluciones
Para evitar estos problemas surgieron dos soluciones:
+ **Diccionario de datos:** conjunto de metadatos que describe los datos y cómo están organizados en una base de datos o en otro tipo de sistema de almacenamiento de datos.
+ **Catálogo:** colección de metadatos que describe la estructura y el contenido de las bases de datos almacenadas en el sistema.

## 2.Diccionario de datos
Un Diccionario de Datos (DD) es un repositorio centralizado de información que almacena metadatos, es decir, datos sobre los propios datos. Este contiene detalles sobre los datos, como su significado, tipos de datos, formatos, tamaños, restricciones... Además, puede incluir información sobre otros elementos relacionados, como los programas que utilizan esos datos o los usuarios que tienen acceso a ellos.

La gestión de la información se realiza de manera centralizada, lo que significa que puede ser consultado y modificado por usuarios con ciertos privilegios. Esto mejora la autenticidad de la información y facilita la comunicación entre los usuarios.

### 2.1.Utilidades
El DD permite:
+ Documentar el modelo de datos, incluyendo requisitos, especificaciones y diseño.
+ Generar informes sobre cualquier elemento del modelo de datos, incluidos los elementos relacionados.
+ Analizar el impacto de un cambio en el modelo de datos, como cambios en los tipos de datos o la inclusión de nuevos elementos.
+ Generar automáticamente la estructura de la BBDD.
+ Generar automáticamente la definición de datos en lenguajes de programación que acceden a esos datos, por ejemplo en clases de Java.

## 3.Catálogo del sistema
El catálogo del sistema es un conjunto de tablas y vistas que almacenan metadatos sobre la base de datos. Se suelen llamar tablas o vistas del sistema para diferenciarlas de las tablas o vistas de usuario.

Es creado y utilizado por el SGBD y es de solo lectura para los usuarios. Los usuarios hacen modificaciones en el catálogo al realizar operaciones DDL.