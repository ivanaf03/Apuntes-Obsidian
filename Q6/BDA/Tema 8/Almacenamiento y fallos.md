[[Tema 8-Recuperación]]
$\space$
## 1.Tipos de almacenamiento
Existen tres tipos de almacenamiento:
+ **Almacenamiento volátil:** su contenido se pierde ante caídas del sistema. Por ejemplo, la RAM, las cachés, la CPU, etc.
+ **Almacenamiento no volátil:** su contenido solo se pierde ante fallos físicos. Por ejemplo, los discos duros.
+ **Almacenamiento estable:** es una idealización en la que nunca se pierde la información. Se puede simular mediante copias de seguridad.
$\space$
## 2.Acceso a datos y operaciones
Los datos se guardan en disco y se envían mediante bloques, también llamados páginas, a memoria. El SGBD maneja el buffer caché de la memoria. 
$\space$
### 2.1.Transferencia entre buffer caché y disco
Pueden darse:
+ **Inputs:** se lee el bloque en disco y se envía a memoria.
+ **Outputs:** se escribe el contenido del bloque en disco.
$\space$
### 2.2.Lectura y escritura de datos desde el programa
+ **Read(X, x):** se da a la variable x del programa el dato X del buffer. Si no está X en el buffer se recupera de disco. 
+ **Write(X, x):** asigna a la variable X del buffer el valor de x. Si X no está en el buffer se recupera de disco.
$\space$
### 2.3.Fallos
Pueden darse fallos mientras ocurren estas cosas:
+ **Fallos sin pérdida de almacenamiento:** no se pierden datos, pero la BBDD puede quedar inconsistente.
+ **Fallos con pérdida de almacenamiento volátil:** existen archivos con los datos, pero pueden no ser consistentes con la BBDD.
+ **Fallos con pérdida de almacenamiento no volátil:** fallos en los archivos de la base de datos.