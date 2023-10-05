[[Tema 3-Diseño e implementación de la capa modelo]]

### Pasos
1. Agrupar los casos de uso de forma lógica
2. Definir una interfaz por cada grupo. Cada caso de uso equivale a un método. Cada interfaz es una aplicación del patrón fachada.

##### Fachada de casos de uso
| **\<\<interface>> MovieService**                  |
|--------------------------------------------|
| + addMovie(movie: Movie) : Movie            |
| + updateMovie(movie: Movie) : void          |
| + removeMovie(movieId : Long) : void        |
| + findMovie(movieId : Long) : Movie         |
| + findMovies(keywords : String) : List\<Movie>|
| + buyMovie(movieId : Long, userId : String, creditCardNumber : String) : Sale |
| + findSale(saleId : Long) : Sale            |

### Ventajas
+ Al definirse como una interfaz permite tener implementaciones alternativas.
+ En una fase temprana de desarrollo se podría presentar una implementación ficticia.
+ Permite al resto de equipo de desarrollo encargarse de otras cosas.