[[Tema 2-JDBC Conectividad de bases de datos con java]]

### Interfaz Connection
Representa una conexión a la BD
+ prepareStatement: permite construir objetos
+ PreparedStatement: lanzador de consultas

### Interfaz PreparedStatement
Contiene la consulta SQL y métodos setter para dar valores a los parámetros.
+ executeUpdate: permite lanzar consultas SQL y devuelve el número de filas afectadas
+ executeQuery: permite lanzar lecturas SQL

### Formateo de datos en PreparedStatement
Es el driver quien formatea los datos, no es desarrollador. Cada base de datos tiene su driver con el formato adecuado.

### SQLException
Los métodos de JDBC reportan los errores lanzando una SQLException o excepciones derivadas.

### Interfaz ResultSet
Representa todas las filas que coinciden con la búsqueda de la consulta. Si no quedan filas por leer next, un cursor iterador, devuelve false. Contiene métodos getter para acceder a los valores de las columnas de la fila en la que se encuentra el cursor.

### Clase ConnectionManager
Permite obtener conexiones con la API de JDBC. En un caso real, la URL de conexión, el usuario y la contraseña se guardan en un fichero de configuración a parte para que no sea necesario modificar el código al cambiar estos parámetros.

### Liberación de recursos
Los ejemplos cierran la conexión de forma implícita. Utilizan un try-with-resources, que cierra la conexión sin necesidad del típico finally. 

La implementación de Connection debe redifinir finally para que invoque a close si el desarrollador no lo ha hecho.

En un caso real esto no sería buena idea porque las aplicaciones son multithread y con un número de usuarios muy grande, habría inanición. Cada thread debe liberar la conexión inmediatamente tras interactuar con la base de datos.