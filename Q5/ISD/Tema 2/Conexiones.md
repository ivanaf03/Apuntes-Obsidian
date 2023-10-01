[[Tema 2-JDBC Conectividad de bases de datos con java]]

### DataSources
Es una interfaz que dispone del método getConnection. Se utiliza para pedir una conexión sin especifficar URL, usuario o contraseña. 

Se utiliza en servidores de aplicaciones y algunos frameworks. Utilizan ficheros de configuración para especificar la URL, el usuario y la contraseña. Para implementarlo se utiliza DriverManager.getConnection.

### Pool de conexiones
Cuando se reciben muchas peticiones HTTP puede haber cuellos de botella. Para solucionar esto se utiliza un pool de conexiones. Se trabaja con la interfaz DataSource, ya que utiliza esta estrategia.

##### ConnectionPool
Al crearlo, este pide n conexiones a la BD con DriverManager.getConnection y se almacenan en una lista. Consta de los métodos getConnection, que devuelve un ConnectionProxy si queda alguno libre y, si no, deja durmiendo al thread que llama; y releaseConnection, que devuelve la conexión a la lista y avisa a los thread que la esperan.

##### ConnectionProxy
Es un proxy de la conexión real. Tiene los métodos close, que libera la conexión; y finalize, que si no se ha llamado a close, lo llama.

### Caídas de la BD
Si la BD se cae, todas las conexiones del pool se invalidan. Para revisar que la conexión está viva, se pueden utilizar 2 trucos:
+ Utilizar alguna función de la API del driver
+ Lanzar una consulta poco costosa a la BD y comprobar que no se produce una SQLException

