[[Tema 8-Recuperación]]
$\space$
## 1.Ficheros de log
Los ficheros de log son pequeños ficheros que guardan los cambios realizados en la base de datos. Contienen:
+ Id de transacción.
+ Tipo de registro:
	+ Start
	+ Commit o rollback de fin de transacción
	+ Modificación de datos
+ Para registros de modificación id del dato, valor anterior y valor posterior.
$\space$
### 1.1.Opciones de recuperación
Cuando hay errores el sistema decide que hacer:
+ **Undo:** deshace los cambios de la transacción en orden inverso.
+ **Redo:** vuelve a hacer la transacción en orden secuencial.
$\space$
### 1.2.Actualizaciones
Los ficheros de log se utilizan con 2 técnicas:
+ Actualizaciones inmediatas
+ Actualizaciones diferidas
$\space$
#### 1.2.1.Actualizaciones inmediatas
Se escribe en el registro del log y después se modifica el dato en los buffers. Si ocurre un fallo antes de terminar la transacción puede haber que deshacer cambios.

Si una transacción acaba confirmándose hay que hacer redo porque no sabemos si se llevaron a disco los cambios. Si acaba sin confirmar hay que hacer undo.

Como se necesita hacer undo y redo los ficheros de log necesitan la imagen anterior y posterior de cada dato. Tienen el formato `T, dato, anterior, posterior`.

![[actu inmediata.png]]
$\space$
#### 1.2.2.Actualizaciones diferidas
Se escribe en el fichero de log, pero no se modifican los datos hasta terminar la transacción. Evita tener que deshacer cambios.

Si una transacción acaba confirmándose hay que hacer redo porque no sabemos si se llevaron a disco los cambios. Si acaba sin confirmar no hay que hacer nada porque no se llevaron los datos a disco.

Como solo se necesita hacer redo los ficheros de log necesitan solo la imagen posterior de cada dato. Tienen el formato `T, dato, posterior`.

![[actu diferida.png]]
$\space$
## 2.Checkpoints
Un checkpoint es una grabación de los datos de los buffers en disco. Se hacen de forma periódica para reducir el tiempo de recuperación y liberar los ficheros de logs. 
$\space$
### 2.1.Acciones
Un checkpoint:
1. Suspende las transacciones.
2. Escribe en los ficheros de log los buffers modificados.
3. Escribe en base de datos (en disco) el buffer modificado.
4. Escribe en el log un registro de las transacciones activas.
5. Restaura la ejecución.
$\space$
## 3.Recuperación
Al usar checkpoint se puede ignorar la recuperación de todas las transacciones acabadas antes de su creación. Para recuperar las transacciones solo es necesario tener en cuenta las posteriores al checkpoint y las que estaban en curso.
$\space$
### 3.1.Protocolo WAL
El protocolo write ahead logging especifica que siempre debe registrarse antes el cambio en los logs que en la base de datos física.

Para ello se debe modificar el buffer de log antes que el buffer de datos. Además, cuando se vierte un buffer de datos en disco previamente se deben haber vertido los registros de buffer de log.

El objetivo es que toda la información para undo y redo se guarde antes de hacer los cambios. Si se hubieran pasado antes los cambios a disco no habría información para el redo o undo en caso de que hubiera errores.
$\space$
### 3.2.Confirmación
Cuando se hace un commit se vierten los buffers de log de la transacción al fichero de log antes de la confirmación. Después se vuelcan los buffers de datos mediante las siguientes estrategias (aunque se suele usar robar y no forzar):
+ **Robar/ no robar:** robar permite pasar páginas de datos a disco antes de que termine una transacción. No robar obliga a confirmar primero.
+ **Forzar/ no forzar:** forzar obliga a pasar a disco todas las páginas al confirmar.
$\space$
### 3.3.Tipos de logs
Los logs pueden ser:
+ Offline
+ Online
$\space$
#### 3.3.1.Logs online
Son los ficheros físicos que utiliza la base de datos para implementar el log de base de datos. Tienen tamaño fijo y se pueden multiplexar, es decir, tener varias copias.

Funcionan de forma cíclica. Cuando se llenan se empiezan a sobrescribir los datos más antiguos. 
$\space$
#### 3.3.2.Logs offline
Para aumentar la ventana de recuperación que permiten los logs online se implementan los logs offline. Son copias en otra ubicación para mantener un histórico de logs. Se suelen grabar en medios de solo lectura.
$\space$
### 3.4.Proceso de recuperación
Para realizar al completo la recuperación es necesaria una copia de seguridad. El proceso es el siguiente:
+ Se restauran los ficheros de logs.
+ Se usan las actualizaciones inmediatas o diferidas mediante los logs online u offline. 
+ Si se ha dañado la configuración de gestor, será necesaria una reinstalación.



