[[Tema 8-Recuperación]]
$\space$
## 1.Qué es una copia de seguridad?
Una copia de seguridad o backup es una copia de datos almacenada en un soporte diferente que se puede usar para restaurar los datos originales después de una pérdida.
$\space$
### 1.1.Pérdida de toda la información
Cuando ocurre un fallo catastrófico y se pierde toda la información se debe hacer un backup de:
+ Software, por ejemplo, el SGBD.
+ Ficheros de configuración y ficheros auxiliares del SGBD.
+ Ficheros de datos de la BD.
+ Logs offline.
$\space$
### 1.2.Cómo se hacen las copias de seguridad?
Las copias de seguridad se hacen con herramientas de backup del sistema. Se pueden utilizar para los ficheros de datos y logs offline, realizando simplemente copias físicas de los ficheros. Puede dar lugar a inconsistencias si durante un fallo hay transacciones activas y no se han pasado los cambios de memoria a disco.

Los logs online se están actualizando constantemente cuando se realizan operaciones en la base de datos. Hacer copias de seguridad de ellos puede ser muy complicado y puede crear interrupciones o problemas de rendimiento. En lugar de hacer backups se hace multiplexación, es decir, se mantienen varias copias de cada fichero de log.
$\space$
## 2.Proceso de recuperación
La recuperación depende del tipo de fallo.
$\space$
### 2.1.Fallo sin pérdida de almacenamiento no volátil
Basta con aplicar los logs online.
$\space$
### 2.2.Fallo con pérdida de almacenamiento no volátil
Son necesarias las copias de seguridad. Primero se revisa si es necesaria la reinstalación del software. Si no, se restauran los ficheros de datos del último backup. Mediante los logs se devuelve a la base de datos al último estado consistente.
$\space$
## 3.Backups
Los backups se pueden hacer tanto con herramientas de exportación como físicamente. Con herramientas de exportación se crean snapshots de los datos. No ven los datos que están sin confirmar en otras transacciones y no se pueden combinar con los logs. Sirven para restaurar la base de datos a un momento puntual.

Por otro lado están los backups físicos. Sirven para guardar los logs offline, a parte de hacer una copia física de los ficheros de la base de datos.
$\space$
### 3.1.Periodicidad de backups
Los backups se hacen periódicamente. Pueden ser:
+ **Completos:** copia completa de todos los ficheros de datos.
+ **Incrementales:** copia de los bloques de datos modificados desde el último backup.



