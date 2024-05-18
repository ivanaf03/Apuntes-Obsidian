[[Tema 8-Recuperación]]
$\space$
## 1.Qué es una transacción?
Una transacción es la unidad lógica de ejecución. Está compuesta por operaciones de escritura y lectura sobre la BBDD.

Son la unidad fundamental para el control de conurrencia.

Puede acabar en:
+ **Commit:** confirma los cambios.
+ **Rollback:** anula los cambios.
$\space$
### 1.1.Estados de una transacción
Una transacción está activa durante la ejecución de las operaciones. Si hace un commit, pasa a parcialmente confirmada. Si el commit tiene éxito, pasa a confirmada. 

Si durante una transacción activa se produce un rollback pasa a fracasada. Tras revertir los cambios pasa a abortada. También puede pasar a fracasada una transacción parcialmente confirmada.
$\space$
## 2.Propiedades ACID
Una transacción debe ser:
+ **Atómica:** se ejecutan todas las operaciones o ninguna.
+ **Consistente:** a transacción lleva a la base de datos siempre de un estado consistente a otro consistente.
+ **Aislada:** son independientes unas de otras.
+ **Persistente:** los cambios confirmados quedan en la BBDD.
$\space$

