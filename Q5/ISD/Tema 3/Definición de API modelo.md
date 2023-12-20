[[Tema 3-Diseño e implementación de la capa modelo]]

## Pasos
1. Agrupar los casos de uso de forma lógica.
2. Definir una interfaz por cada grupo. Cada caso de uso equivale a un método. Cada interfaz es una aplicación del patrón fachada (MovieService).

### Fachada de casos de uso
| **\<\<interface>> MovieService**                  |
|--------------------------------------------|
| + addMovie(movie: Movie) : Movie throws InputValidationException;           |
| + updateMovie(movie: Movie) : void throws InputValidationException, InstanceNotFoundException;         |
| + removeMovie(movieId : Long) : void throws InstanceNotFoundException, MovieNotRemovableException;       |
| + findMovie(movieId : Long) : Movie throws InstanceNotFoundException;        |
| + findMovies(keywords : String) : List\<Movie>|
| + buyMovie(movieId : Long, userId : String, creditCardNumber : String) : Sale throws InstanceNotFoundException, InputValidationException; |
| + findSale(saleId : Long) : Sale throws InstanceNotFoundException, SaleExpirationException;           |

## Ventajas de la API modelo
+ Al definirse como una interfaz permite tener implementaciones alternativas (MovieServiceImplementation).
+ En una fase temprana de desarrollo se podría presentar una implementación ficticia (un mock) que no accede a la BD o los métodos no hacen nada.
+ Permite al resto de equipo de desarrollo encargarse de otras cosas.