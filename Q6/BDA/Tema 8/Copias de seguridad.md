[[Tema 8-Recuperación]]

## 1.Qué es una copia de seguridad?
Una copia de seguridad o backup es una copia de datos almacenada en un soporte diferente que se puede usar para restaurar los datos originales después de una pérdida.

### 1.1.Pérdida de toda la información
Cuando ocurre un fallo catastrófico y se pierde toda la información se debe hacer un backup de:
+ Software, por ejemplo, el SGBD.
+ Ficheros de configuración y ficheros auxiliares del SGBD.
+ Ficheros de datos de la BD.
+ Logs offline.

### 1.2.Cómo se hacen las copias de seguridad?
Las copias de seguridad se hacen con herramientas de backup del sistema. Se pueden utilizar para los ficheros de datos y logs offline, realizando simplemente copias físicas de los ficheros. Puede dar lugar a inconsistencias si durante un fallo hay transacciones activas y no se han pasado los cambios de memoria a disco.

Los logs online se están actualizando constantemente cuando se realizan operaciones en la base de datos. Hacer copias de seguridad de ellos puede ser muy complicado y puede crear interrupciones o problemas de rendimiento. En lugar de hacer backups se hace multiplexación, es decir, se mantienen varias copias de cada fichero de log.

## 2.Proceso de recuperación
