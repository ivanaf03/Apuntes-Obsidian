[[Tema 3-Diseño e implementación de la capa modelo]]

### Definición de entidades
De los casos de uso podemos sacar que hay que guardar en la base de datos información sobre películas y ventas. Por tanto, definimos 2 entidades, películas y ventas.

Cada entidad está formada por atributos privados que modelan el estado, getters y setters. La relación entre Movie y Sale es 1:N.

##### Movie
| **Movie**              |
|--------------------|
| - movieId : Long   |
| - title : String   |
| - runtime : short  |
| - description : String |
| - price : float    |
| - creationDate : LocalDateTime |
| + builders    |
| + getters and setters |

##### Sale
| **Sale** |
|-------------------------|
| - saleId : Long |
| - movieId : Long |
| - userId : String |
| - expirationDate : LocalDateTime |
| - creditCardNumber : String |
| - price : float | 
| - movieUrl : String | 
| - saleDate : LocalDateTime |
| + builders    |
| + getters and setters |