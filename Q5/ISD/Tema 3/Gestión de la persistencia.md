[[Tema 3-Diseño e implementación de la capa modelo]]

## Bases de datos
Para guardar las películas y ventas se usa una base de datos. Cada instancia se guarda en una fila de la tabla que corresponda.

Para representar los casos de uso puede ser necesario tener una serie de operaciones CRUD (create-read-update-delete) u otras relacionadas.

Para facilitar la implementación de los casos de uso, se necesita una abstracción que permita gestionar la persistencia de cada entidad. Debe ocultar la BD concreta que se utilice. Este patrón de diseño se llama DAO (Data Access Object). Conceptualmente un DAO es la capa de acceso a datos.

### Interfaz DAO
| **\<\<Interface>> SqlMovieDao**  |
|----------------|
| create(connection: Connection, movie: Movie): Movie |
| find(connection: Connection, movieId: Long): Movie |
| findByKeywords(connection: Connection, keywords: String): List\<Movie> |
| update(connection: Connection, movie: Movie): void |
| remove(connection: Connection, movieId: Long): void |

Reciben la conexión porque para poder agrupar varias operaciones en una misma transición. Sirven para ocultar la base de datos, pero no su tipo ni la tecnología de acceso.

```
public abstract class AbstractSqlMovieDao implements SqlMovieDao {  
  
    protected AbstractSqlMovieDao() {  
    }  
    @Override  
    public Movie find(Connection connection, Long movieId)  
            throws InstanceNotFoundException {  
        String queryString = "SELECT title, runtime, " + " description, price, creationDate FROM Movie WHERE movieId = ?";  
        try (PreparedStatement preparedStatement = connection.prepareStatement(queryString)) {  
            int i = 1;  
            preparedStatement.setLong(i++, movieId.longValue());  
            ResultSet resultSet = preparedStatement.executeQuery();  
            if (!resultSet.next()) {  
                throw new InstanceNotFoundException(movieId, Movie.class.getName());  
            }  
            i = 1;  
            String title = resultSet.getString(i++);  
            short runtime = resultSet.getShort(i++);  
            String description = resultSet.getString(i++);  
            float price = resultSet.getFloat(i++);  
            Timestamp creationDateAsTimestamp = resultSet.getTimestamp(i++);  
            LocalDateTime creationDate = creationDateAsTimestamp.toLocalDateTime();  
            return new Movie(movieId, title, runtime, description, price, creationDate);  
        } catch (SQLException e) {  
            throw new RuntimeException(e);  
        }  
    }  
  
    @Override  
    public List<Movie> findByKeywords(Connection connection, String keywords) {  
        String[] words = keywords != null ? keywords.split(" ") : null;  
        String queryString = "SELECT movieId, title, runtime, " + " description, price, creationDate FROM Movie";  
        if (words != null && words.length > 0) {  
            queryString += " WHERE";  
            for (int i = 0; i < words.length; i++) {  
                if (i > 0) {  
                    queryString += " AND";  
                }  
                queryString += " LOWER(title) LIKE LOWER(?)";  
            }  
        }  
        queryString += " ORDER BY title";  
        try (PreparedStatement preparedStatement = connection.prepareStatement(queryString)) {  
            if (words != null) {  
                for (int i = 0; i < words.length; i++) {  
                    preparedStatement.setString(i + 1, "%" + words[i] + "%");  
                }  
            }  
            ResultSet resultSet = preparedStatement.executeQuery();  
            List<Movie> movies = new ArrayList<Movie>();  
            while (resultSet.next()) {  
                int i = 1;  
                Long movieId = Long.valueOf(resultSet.getLong(i++));  
                String title = resultSet.getString(i++);  
                short runtime = resultSet.getShort(i++);  
                String description = resultSet.getString(i++);  
                float price = resultSet.getFloat(i++);  
                Timestamp creationDateAsTimestamp = resultSet.getTimestamp(i++);  
                LocalDateTime creationDate = creationDateAsTimestamp.toLocalDateTime(); 
                movies.add(new Movie(movieId, title, runtime, description, price, creationDate));  
            }   
            return movies;  
        } catch (SQLException e) {  
            throw new RuntimeException(e);  
        }  
    }  
  
    @Override  
    public void update(Connection connection, Movie movie)  
            throws InstanceNotFoundException {   
        String queryString = "UPDATE Movie" + " SET title = ?, runtime = ?, description = ?, " + "price = ? WHERE movieId = ?";  
        try (PreparedStatement preparedStatement = connection.prepareStatement(queryString)) {   
            int i = 1;  
            preparedStatement.setString(i++, movie.getTitle());  
            preparedStatement.setShort(i++, movie.getRuntime());  
            preparedStatement.setString(i++, movie.getDescription());  
            preparedStatement.setFloat(i++, movie.getPrice());  
            preparedStatement.setLong(i++, movie.getMovieId());    
            int updatedRows = preparedStatement.executeUpdate();  
            if (updatedRows == 0) {  
                throw new InstanceNotFoundException(movie.getMovieId(), Movie.class.getName());  
            }  
        } catch (SQLException e) {  
            throw new RuntimeException(e);  
        }  
    }  
  
    @Override  
    public void remove(Connection connection, Long movieId)  
            throws InstanceNotFoundException {  
        String queryString = "DELETE FROM Movie WHERE" + " movieId = ?";  
        try (PreparedStatement preparedStatement = connection.prepareStatement(queryString)) {  
            int i = 1;  
            preparedStatement.setLong(i++, movieId);  
            int removedRows = preparedStatement.executeUpdate();  
            if (removedRows == 0) {  
                throw new InstanceNotFoundException(movieId, Movie.class.getName());  
            }  
        } catch (SQLException e) {  
            throw new RuntimeException(e);  
        }  
    }  
}
```

```
public class Jdbc3CcSqlMovieDao extends AbstractSqlMovieDao {  
  
    @Override  
    public Movie create(Connection connection, Movie movie) {  
        String queryString = "INSERT INTO Movie"  
                + " (title, runtime, description, price, creationDate)"  
                + " VALUES (?, ?, ?, ?, ?)";  
        try (PreparedStatement preparedStatement = connection.prepareStatement( queryString, Statement.RETURN_GENERATED_KEYS)) {  
            int i = 1;  
            preparedStatement.setString(i++, movie.getTitle());  
            preparedStatement.setShort(i++, movie.getRuntime());  
            preparedStatement.setString(i++, movie.getDescription());  
            preparedStatement.setFloat(i++, movie.getPrice());  
            preparedStatement.setTimestamp(i++, Timestamp.valueOf(movie.getCreationDate()));  
            preparedStatement.executeUpdate();  
            ResultSet resultSet = preparedStatement.getGeneratedKeys();  
            if (!resultSet.next()) {  
                throw new SQLException("JDBC driver did not return generated key.");  
            }  
            Long movieId = resultSet.getLong(1);  
            return new Movie(movieId, movie.getTitle(), movie.getRuntime(),  
                    movie.getDescription(), movie.getPrice(),  
                    movie.getCreationDate());  
        } catch (SQLException e) {  
            throw new RuntimeException(e);  
        }  
    }  
}
```

### Generación dinámica de claves
Existen varias estrategias para la generación de dinámica de claves numéricas:
+ Mecanismos ofrecidos por las BD.
+ Uso de algoritmos para generar claves numéricas.

 Las claves de tipo String suelen ser concatenaciones de varios campos, como la fecha y hora, un número aleatorio, etc.

Cada BD suele tener un soporte diferente para la generación de claves numéricas. Uno de los métodos es mediante contadores. Otra forma es mediante columnas contador: que permite asignar automáticamente valores únicos y crecientes a estas columnas al insertar nuevos registros en una tabla. Es la que se usa en Movies:

```
CREATE TABLE Movie ( movieId BIGINT NOT NULL AUTO_INCREMENT,...);
```
