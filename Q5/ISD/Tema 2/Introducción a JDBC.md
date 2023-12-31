[[Tema 2-JDBC Conectividad de bases de datos con java]]

## JDBC
Java tiene mecanismos para acceder a bases de datos relacionales. La API de Java que se encarga de esto se llama JDBC. Los paquetes con los que se trabaja Java son java.sql y javax.sql.

Para poder conectarse a la base de datos y lanzar consultas es necesario un driver. Los drivers son ficheros .jar que contienen la implementación de las interfaces de las APIs.

Esto nos permite que, si cambiamos de base de datos, tengamos que cambiar el código, sino simplemente el driver. El problema es que las bases de datos utilizan diferentes dialectos de SQL. Los tipos de datos varían, la generación de IDs es diferente...

Es importante recordar que en JDBC los índices empiezan en 1, no en 0 como en Java u otros lenguajes de programación.

### Ejemplo de uso (insert)
```
public final class InsertExample{
	public static void main(String[] args){
		try (Connection connection = ConnectionManager.getConnection()) {
			String[] movieIdentifiers = new String[] {"movie-1", "movie-2", "movie-3"};
			String[] titles = new String[] {"movie-1 title", "movie-2 title", "movie-3 title"};
			short[] runtimes = new short[] {90, 120, 150};
			String queryString = "INSERT INTO TutMovie " + "(movieId, title, runtime) VALUES (?, ?, ?)";
			PreparedStatement preparedStatement = connection.prepareStatement(queryString);
			for (int i=0; i<movieIdentifiers.length; i++){
				preparedStatement.setString(1, movieIdentifiers[i]);
				preparedStatement.setString(2, titles[i]);
				preparedStatement.setShort(3, runtimes[i]);
				int insertedRows = preparedStatement.executeUpdate();
				if (insertedRows != 1) { 
					throw new SQLException(movieIdentifiers[i] + ": problems when inserting."); 
				}
			}
			System.out.println("Movies inserted");
		} catch (Exception e) {
			e.printStackTrace(System.err);
		}
	}
}
```

### Ejemplo de uso (select)
```
public final class SelectExample {
	public static void main (String[] args) {
		try (Connection connection = ConnectionManager.getConnection()) {
			String queryString = "SELECT movieId, title, runtime FROM TutMovie";
			PreparedStatement preparedStatement = connection.prepareStatement(queryString);
			ResultSet resultSet = preparedStatement.executeQuery();
			while (resultSet.next()) {
				String movieIdentifier = resultSet.getString(1);
				String title = resultSet.getString(2);
				short runtime = resultSet.getShort(3);
				System.out.println("movieIdentifier = " + movieIdentifier + " | title = " + title + " | runtime = " + runtime);
			}
		} catch (Exception e) {
			e.printStackTrace(System.err);
		}
	}
}
```

### ConnectionManager
```
public class ConnectionManager {
	private final static String DRIVER_URL = "jdbc:mysql://localhost/ws?...";
	private final static String USER = "ws";
	private final static String PASSWORD = "ws";
	
	private ConnectionManager() {}

	public final static Connection getConnection(){
		throws SQLException {
			return DriverManager.getConnection(DRIVER_URL, USER, PASSWORD);
		}
	}
}
```

## Ejecución de sentencias
### Interfaz Connection
Representa una conexión con la base de datos. Por ejemplo:
```
Connection connection = ConnectionManager.getConnection()
String queryString = "SELECT movieId, title, runtime FROM TutMovie";
PreparedStatement preparedStatement = connection.prepareStatement(queryString);
```

El método getConnection permite obtener conexión a la base de datos a través de una URL o de un id y una contraseña. En una aplicación real el usuario y la contraseña se leen de un archivo de configuración.

### Interfaz PreparedStatement
Contiene la consulta SQL parametrizada. Dispone de setter para dar valor a los parámetros. Permite lanzar consultas de actualización (executeUpdate) o de lectura (executeQuery).

El driver se encarga de formatear los datos. Por ejemplo, lanzaría:
```
INSERT INTO TutMovie (movieId, title, runtime) VALUES ('movie-1', 'movie-1 title', 90)

INSERT INTO User (birthdate, ...) VALUES ('2015-09-01', ...)
```

### SQL Exception
Los métodos de la API lanzan una SQLException ante cualquier error.
```
if (insertedRows != 1) { 
	throw new SQLException(movieIdentifiers[i] + ": problems when inserting."); 
}
```

### Interfaz ResultSet
Representa todas las filas que concuerdan con la búsqueda. Funciona como una especie de cursor. El método next avanza y devuelve true si quedan filas por leer. Contiene getters para acceder a los valores de la fila donde se encuentra el cursor.
```
while (resultSet.next()) {
	String movieIdentifier = resultSet.getString(1);
	String title = resultSet.getString(2);
	short runtime = resultSet.getShort(3);
	System.out.println("movieIdentifier = " + movieIdentifier + " | title = " + title + " | runtime = " + runtime);
}
```

## Liberación de recursos
Para abrir y cerrar las conexiones los ejemplos anteriores usan try-with-resources. Los recursos se declaran entre los paréntesis del try. El compilador de java llama al método close siempre que termine el bloque try.

En caso de utilizar el try normal, habría que cerrar la conexión manualmente. Para ello, se redefine finalize en la interfaz Connection.

```
Connection connection = null;
try { 
	connection = ConnectionManager.getConnection(); 
	...
} catch (Exception e) { 
	e.printStackTrace(System.err);
 } finally {
	try {
		if (connection != null) { 
			connection.close(); 
		} 
	} catch (Exception e) {
		e.printStackTrace(System.err); 
	} 
}
```

Si no se liberan las conexiones, en un caso real podría llegar un momento en el que se hayan procesado demasiadas peticiones HTTP de accesos a la BD sin que el recolector de basura las haya liberado. Cuando llegue la siguiente petición devolverá SQLException porque no admite más conexiones.