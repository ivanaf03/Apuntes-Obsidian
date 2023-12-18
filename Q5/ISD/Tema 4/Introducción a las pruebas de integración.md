[[Tema 4-Pruebas de integración de la capa modelo]]

## Independencia entre casos de prueba
Para que el código se pueda mantener es recomendable que cada caso de prueba cumpla ciertos aspectos: 
+ Crea los datos que necesita.
+ Invoca la operación que tiene que testear.
+ Realiza las comprobaciones necesarias.
+ Elimina los datos generados.

Con esto conseguimos que cada caso de prueba sea independiente. Para evitar redundancias definimos métodos privados como createMovie, removeMovie o removeSale.

## Uso de bases de datos
Es una buena práctica tener varias bases de datos:
+ Una base de datos para probar en la fase de desarrollo (ws).
+ Una base de datos para las pruebas automatizadas (wstest).
+ Una base de datos para producción.

## JUnit5
Las pruebas de unidad se centran en verificar el correcto funcionamiento de unidades individuales de código, como funciones, métodos o clases. En cambio, las pruebas de integración se centran en verificar que las unidades de código se combinan correctamente y funcionan adecuadamente en conjunto como un conjunto más grande.

Los test que se deben hacer son de integración. Verifican el funcionamiento correcto de MovieService y de los DAOs. 

### AssertEquals
El método Assertions.assertEquals compara dos objetos utilizando el método equals de Object. Por defecto comprueba si dos objetos apuntan al mismo sitio. 

Para que haga comparaciones por contenido, se redefine el método equals. La implementación debe devolver true si todos los campos de ambos objetos son iguales. Al redefinir equals, también se debe redefinir el hashcode.

### Inicialización
En los test se usan las variables movieService y saleDao. Se deben definir antes de nada. Para ello se utiliza la anotación @BeforeAll.
```
@BeforeAll  
public static void init() {  
	DataSource dataSource = new SimpleDataSource();  
    DataSourceLocator.addDataSource(MOVIE_DATA_SOURCE, dataSource);  
    movieService = MovieServiceFactory.getService();  
    saleDao = SqlSaleDaoFactory.getDao();  
}
```