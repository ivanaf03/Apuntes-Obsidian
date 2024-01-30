[[Catálogo]]

## Metadatos
Un sistema de información suele plasmar conocimiento sobre un dominio. Están formados por ficheros y programas que los manejan. 

Suele haber dos tipos de metadatos:
+ **Diccionario de datos:** 
+ **Catálogo:** lo crea la base de datos. Lo mantiene el propio sistema y los usuarios no pueden modificarlo.

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
Es un conjunto de tablas que almacenan metadatos sobre la base de datos y los exponen de forma amigable. Se suelen llamar tablas o vistas del sistema.

Es creado por el SGBD y es de solo lectura para los usuarios. Se pueden hacer modificaciones en el catálogo, por ejemplo, creando una tabla.

