[[Tema 3-Capa lógica de negocio con Spring]]

# 1.Problemática
Cuando hay mucha carga computacional no es escalable trabajar con niveles de aislamiento superiores a `TRANSACTION_READ_COMMITED`. Las bases de datos tendrían que hacer demasiados bloqueos en las filas afectadas por una transacción para garantizar aislamiento.

Hibernate asume que no se utiliza un nivel de aislamiento superior a `TRANSACTION_READ_COMMITED`. Por tanto:
+ [>] Puede haber problemas de second lost update, non-repeatable reads y phantom reads.
+ [>] Simultáneamente suele haber varias transacciones que hacen lecturas en la BD, actualizaciones en memoria y escrituras en la BD. Esto produce second lost update. 

# 2.Solución con Optimistic Locking
La solución más simple es añadir a la entidad una propiedad anotada con `@Version`. El valor de este atributo lo maneja automáticamente el mapeador objeto-relacional. Cuando se inserta una instancia de una entidad en BD e atributo toma el valor 0. Al recuperarla a memoria se recupera también el valor de versión. Al actualizar una instancia de la entidad se lanza una consulta de este estilo:

```sql
UPDATE Entity
SET <<columnas>>, version=version+1 
WHERE id=<<id entidad>> AND version=<<valor de version en memoria>>;
```

Si el número de filas actualizadas es 0 el mapeador lanza una `RuntimeException`. Por debajo `PreparedStatement.executeUpdate` devuelve el número de filas afectadas por la consulta.

## 2.1.Ventajas
+ [p] La estrategia es escalable porque no se realizan bloqueos sobre las filas que se leen en la transacción.
+ [p] La excepción puede subir a capas superiores e informar al usuario de que no se ejecutó su operación.