[[Tema 3-Diseño e implementación de la capa modelo]]

## Implementación mediante los DAO
La implementación de los servicios corresponde  a la capa lógica de negocio. Debemos tener en cuenta:
+ Gestión de transacciones.
+ Obtención de referencias a DataSource.
+ Obtención de referencias a DAOs.
+ Obtención de referencias al propio servicio desde el cliente.

### Gestión de transacciones e implementación
+ Para casos de uso que solo ejecutan una operación de lectura contra la BD: auto-commit y nivel de aislamiento por defecto (findMovie y findMovies).
+ Resto de casos: 
	1. Validar datos de entrada
	2. Empezar transacción serializable
	3. Comprobar que es posible ejecutarlo
	4. Si no es posible: commit+checked
	5. Implementar la capa lógica de negocio
	6. Si hay un error grave: rollback
	7. En cualquier otro caso: commit

```
public class MovieServiceImpl implements MovieService {  
    private final DataSource dataSource;  
    private SqlMovieDao movieDao = null;  
    private SqlSaleDao saleDao = null;  
  
    public MovieServiceImpl() {  
       dataSource = DataSourceLocator.getDataSource(MOVIE_DATA_SOURCE);  
       movieDao = SqlMovieDaoFactory.getDao();  
       saleDao = SqlSaleDaoFactory.getDao();  
    }  
  
    private void validateMovie(Movie movie) throws InputValidationException {  
       PropertyValidator.validateMandatoryString("title", movie.getTitle());  
       PropertyValidator.validateLong("runtime", movie.getRuntime(), 0, MAX_RUNTIME);  
       PropertyValidator.validateMandatoryString("description", movie.getDescription());  
       PropertyValidator.validateDouble("price", movie.getPrice(), 0, MAX_PRICE);  
    }  
  
    @Override  
    public Movie addMovie(Movie movie) throws InputValidationException {  
       validateMovie(movie);  
       movie.setCreationDate(LocalDateTime.now());  
       try (Connection connection = dataSource.getConnection()) {  
          try {       connection.setTransactionIsolation(Connection.TRANSACTION_SERIALIZABLE);  
             connection.setAutoCommit(false);  
             Movie createdMovie = movieDao.create(connection, movie); 
             connection.commit();  
             return createdMovie;  
          } catch (SQLException e) {  
             connection.rollback();  
             throw new RuntimeException(e);  
          } catch (RuntimeException | Error e) {  
             connection.rollback();  
             throw e;  
          }  
       } catch (SQLException e) {  
          throw new RuntimeException(e);  
       }  
    }  
  
    @Override  
    public void updateMovie(Movie movie) throws InputValidationException, InstanceNotFoundException {  
       validateMovie(movie);  
       try (Connection connection = dataSource.getConnection()) {  
          try {              connection.setTransactionIsolation(Connection.TRANSACTION_SERIALIZABLE);  
             connection.setAutoCommit(false);
             movieDao.update(connection, movie);  
             connection.commit();  
          } catch (InstanceNotFoundException e) {  
             connection.commit();  
             throw e;  
          } catch (SQLException e) {  
             connection.rollback();  
             throw new RuntimeException(e);  
          } catch (RuntimeException | Error e) {  
             connection.rollback();  
             throw e;  
          }  
       } catch (SQLException e) {  
          throw new RuntimeException(e);  
       }  
    }  
  
    @Override  
    public void removeMovie(Long movieId) throws InstanceNotFoundException, MovieNotRemovableException {  
       try (Connection connection = dataSource.getConnection()) {  
          try {            connection.setTransactionIsolation(Connection.TRANSACTION_SERIALIZABLE);  
             connection.setAutoCommit(false);  
             if (saleDao.existsByMovieId(connection, movieId)) {  
                throw new MovieNotRemovableException(movieId);  
             }  
             movieDao.remove(connection, movieId);  
             connection.commit();  
          } catch (InstanceNotFoundException | MovieNotRemovableException e) {  
             connection.commit();  
             throw e;  
          } catch (SQLException e) {  
             connection.rollback();  
             throw new RuntimeException(e);  
          } catch (RuntimeException | Error e) {  
             connection.rollback();  
             throw e;  
          }  
       } catch (SQLException e) {  
          throw new RuntimeException(e);  
       }  
    }  
  
    @Override  
    public Movie findMovie(Long movieId) throws InstanceNotFoundException {  
       try (Connection connection = dataSource.getConnection()) {  
          return movieDao.find(connection, movieId);  
       } catch (SQLException e) {  
          throw new RuntimeException(e);  
       }  
    }  
  
    @Override  
    public List<Movie> findMovies(String keywords) {  
       try (Connection connection = dataSource.getConnection()) {  
          return movieDao.findByKeywords(connection, keywords);  
       } catch (SQLException e) {  
          throw new RuntimeException(e);  
       }  
    }  
  
    @Override  
    public Sale buyMovie(Long movieId, String userId, String creditCardNumber)  
          throws InstanceNotFoundException, InputValidationException {  
       PropertyValidator.validateCreditCard(creditCardNumber);  
       try (Connection connection = dataSource.getConnection()) {  
          try {    connection.setTransactionIsolation(Connection.TRANSACTION_SERIALIZABLE);  
             connection.setAutoCommit(false);  
             Movie movie = movieDao.find(connection, movieId);  
             LocalDateTime expirationDate = LocalDateTime.now().plusDays(SALE_EXPIRATION_DAYS);  
             Sale sale = saleDao.create(connection, new Sale(movieId, userId, expirationDate, creditCardNumber,  
                   movie.getPrice(), getMovieUrl(movieId), LocalDateTime.now()));  
             connection.commit();  
             return sale;  
          } catch (InstanceNotFoundException e) {  
             connection.commit();  
             throw e;  
          } catch (SQLException e) {  
             connection.rollback();  
             throw new RuntimeException(e);  
          } catch (RuntimeException | Error e) {  
             connection.rollback();  
             throw e;  
          }  
       } catch (SQLException e) {  
          throw new RuntimeException(e);  
       }  
    }  
  
    @Override  
    public Sale findSale(Long saleId) throws InstanceNotFoundException, SaleExpirationException {  
       try (Connection connection = dataSource.getConnection()) {  
          Sale sale = saleDao.find(connection, saleId);  
          LocalDateTime now = LocalDateTime.now();  
          if (sale.getExpirationDate().isAfter(now)) {  
             return sale;  
          } else {  
             throw new SaleExpirationException(saleId, sale.getExpirationDate());  
          }  
       } catch (SQLException e) {  
          throw new RuntimeException(e);  
       }  
    }  
  
    private static String getMovieUrl(Long movieId) {  
       return BASE_URL + movieId + "/" + UUID.randomUUID().toString();  
    }  
}
```

### DataSources
Es necesario obtener una referencia a un DataSource:
+ En las pruebas de integración de la capa modelo. Es desarrollador se lo proporciona.
+ Cuando se ejecuta la capa modelo dentro de una aplicación o servicio web. Es proporcionado por el pool de conexiones.

Para ello se crea la clase DataSourceLocator:
```
public static final String MOVIE_DATA_SOURCE = "ws-javaexamples-ds";
dataSource = DataSourceLocator.getDataSource(MOVIE_DATA_SOURCE);  
```

### Referencias a DAOs
Para poder tener una referencia a un dato independientemente de su implementación, utilizamos el patrón factoría:
```
movieDao = SqlMovieDaoFactory.getDao();  
saleDao = SqlSaleDaoFactory.getDao(); 
```

```
public class SqlMovieDaoFactory {  
  
    private final static String CLASS_NAME_PARAMETER = "SqlMovieDaoFactory.className";  
    private static SqlMovieDao dao = null;  
  
    private SqlMovieDaoFactory() {  
    }  
    
    @SuppressWarnings("rawtypes")  
    private static SqlMovieDao getInstance() {  
        try {  
            String daoClassName = ConfigurationParametersManager  .getParameter(CLASS_NAME_PARAMETER);  
            Class daoClass = Class.forName(daoClassName);  
            return (SqlMovieDao) daoClass.getDeclaredConstructor().newInstance();  
        } catch (Exception e) {  
            throw new RuntimeException(e);  
        }   
    }  
  
    public synchronized static SqlMovieDao getDao() {  
        if (dao == null) {  
            dao = getInstance();  
        }  
        return dao;  
    }  
}
```

Las factorías tratan a los DAOs como singletons, objetos sin estado que pueden ser utilizados por múltiples threads. Si se desea utilizar otra manera de generar identificadores numéricos o se cambia a otra base de datos donde no sirva el DAO especificado, bastaría con modificar la implementación de este.