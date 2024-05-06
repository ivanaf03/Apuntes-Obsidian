[[Tema 1-Catálogo]]
$\space$$\space$
## 1.Sistemas de información
Un sistema de información es un conjunto ordenado de mecanismos que sirve para administrar datos e información.
$\space$$\space$
### 1.1.Por qué son necesarios los metadatos?
Antes los sistemas de información estaban formados por ficheros y por los propios programas que los manejaban. La estructura y la descripción de los datos estaba en el código de los programas.

Gracias a los metadatos podemos entender, gestionar, proteger y mantener fácilmente una base de datos.
$\space$$\space$
#### 1.1.1.Inconvenientes de los sistemas de información antiguos
Si siguiéramos utilizando esta metodología:
+ [c] Podría haber incompatibilidad entre los datos al usarlos en varios programas.
+ [c] No hay documentación suficiente sobre los datos, los procesos que los usan, los permisos de acceso a ellos, etc.
$\space$$\space$
#### 1.1.2.Alternativas a esta metodología
Surgieron dos alternativas:
+ **Diccionario de datos:** conjunto de metadatos que describe los datos y explica como están organizados en una BBDD o en otro tipo de sistema de almacenamiento de datos.
+ **Catálogo:** colección de metadatos que describe la estructura y el contenido de las bases de datos del sistema.
$\space$$\space$
## 2.Diccionario de datos
Un Diccionario de Datos (DD) es un repositorio centralizado de información que almacena metadatos. Este contiene información sobre los datos, como su significado, tipos de datos, formatos, tamaños, restricciones, etc. 

A veces se incluye otra información, como qué programas utilizan los datos o que usuarios pueden acceder a ellos.
$\space$$\space$
### 2.1.Funciones
El DD sirve para:
+ Documentar el modelo propuesto.
+ Generar informes sobre los elementos del modelo.
+ Analizar el impacto de un cambio en el modelo de datos.
+ Generar de forma automática la estructura de la base de datos.
+ Generar de forma automática la definición de datos en lenguajes de programación que necesiten los datos.
$\space$$\space$
## 3.Catálogo del sistema
El catálogo del sistema es un conjunto de tablas y vistas que almacenan metadatos sobre la base de datos. Se suelen llamar tablas o vistas del sistema para diferenciarlas de las tablas o vistas de usuario.

Lo crea y actualiza el SGBD y es de solo lectura para los usuarios.
$\space$$\space$
### 3.1.Modificaciones indirectas en el catálogo
Las operaciones DDL (Data Definition Language) son un conjunto de comandos utilizados para definir y gestionar la estructura de la base de datos. Son aquellas que permiten crear, modificar y eliminar objetos de base de datos como tablas, índices, vistas, etc.

Al realizar operaciones DDL los usuarios realizan de forma indirecta modificaciones en el catálogo.