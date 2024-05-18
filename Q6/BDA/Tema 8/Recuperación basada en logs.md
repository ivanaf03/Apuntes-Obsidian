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
$\space$
#### 1.2.2.Actualizaciones diferidas
Se escribe en el fichero de log, pero no se modifican los datos hasta terminar la transacción. Evita tener que deshacer cambios.


