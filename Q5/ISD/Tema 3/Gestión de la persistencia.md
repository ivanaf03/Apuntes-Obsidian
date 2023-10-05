[[Tema 3-Diseño e implementación de la capa modelo]]

### Base de datos
Para guardar las películas y ventas se usa una base de datos. Cada instancia se guarda en una fila de la tabla que corresponda.

Para representar los casos de uso puede ser necesario tener una serie de operaciones CRUD (create-read-update-delete) u otras relacionadas.

Para facilitar la implementación de los casos de uso, se necesita una abstracción que permita gestionar la persistencia de cada entidad. Debe ocultar la BD concreta que se utilice. Este patrón de diseño se llama DAO (Data Access Object). Conceptualmente un DAO es la capa de acceso a datos.

##### Interfaz DAO
| **\<\<Interface>> SqlMovieDao**  |
|----------------|
| create(connection: Connection, movie: Movie): Movie |
| find(connection: Connection, movieId: Long): Movie |
| findByKeywords(connection: Connection, keywords: String): List\<Movie> |
| update(connection: Connection, movie: Movie): void |
| remove(connection: Connection, movieId: Long): void |

Reciben la conexión porque para poder agrupar varias operaciones en una misma transición. Sirven para ocultar la base de datos, pero no su tipo ni la tecnología de acceso.

##### Generación dinámica de claves
Existen varias estrategias para la generación de dinámica de claves numéricas:
+ Mecanismos ofrecidos por las BD
+ Uso de algoritmos para generar claves numéricas

 Las claves de tipo String suelen ser concatenaciones de varios campos, como la fecha y hora, un número aleatorio, etc.

Cada BD suele tener un soporte diferente para la generación de claves numéricas. Uno de los métodos es mediante contadores. Otra forma es mediante columnas contador: cada vez que se inserta una fila, se le asigna un valor a la columna contador. Para poder leer el valor se puede haceer una consulta especial o se puede usar la API de JDBC 3.0+.