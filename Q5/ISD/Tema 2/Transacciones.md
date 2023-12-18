[[Tema 2-JDBC Conectividad de bases de datos con java]]

## ¿Qué es una transacción?
Una transacción es una secuencia de operaciones de bases de datos que se ejecutan como una unidad atómica e indivisible. Esto significa que todas las operaciones dentro de una transacción se completan con éxito o se deshacen por completo, de modo que la base de datos se mantiene en un estado coherente y consistente, incluso en situaciones de error. Se basan en las propiedades ACID.

Por defecto, una conexión se crea en auto-commit, es decir, que cada consulta lanzada se ejecuta en su propia transacción. Para ejecutar varias en una sola transacción se desactiva el modo auto-commit y se hace el commit o rollback necesario cuando toque.

```
public final class TransactionExample {
	public static void main (String[] args) {
		try (Connection connection = ConnectionManager.getConnection()){
			try {
				connection.setAutoCommit(false);
				//Insertar películas
				connection.commit();
				System.out.println("Movies inserted");
			} catch (Exception e) {
				connection.rollback();
				throw e;
			}
		} catch (Exception e) {
			e.printStackTrace(System.err);
		}
	}
}
```

## Niveles de aislamiento
Connection proporciona el método setTransactionIsolation, que permite especificar el nivel de aislamiento a:
+ **TRANSACTION_NONE:** transacciones no soportadas.
+ **TRANSACTION_READ_UNCOMMITTED:** pueden ocurrir dirty reads, non-repeatable reads y phantom reads.
+ **TRANSACTION_READ_COMMITTED:** pueden ocurrir non repeatable reads y phantom reads.
+ **TRANSACTION_REPEATABLE_READ:** pueden ocurrir phantom reads. 
+ **TRANSACTION_SERIALIZABLE:** elimina todos los problemas de concurrencia (la que se usa en la asignatura)