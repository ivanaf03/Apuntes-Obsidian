[[Tema 6-Diseño e implementación de servicios web REST]]

## Diseño por capas
+ **Interfaz de usuario:** Lógica de la aplicación cliente. No depende de la tecnología de acceso a servicio.
+ **Acceso a servicio:** API que oculta la tecnología usada para acceder a los servicios.
+ **Servicios:** implementación de los servicios que delega en la capa modelo.
+ **Modelo:** lógica de la aplicación. No depende de la tecnología de implementación de los servicios.

### Capa servicios
La capa de servicios utiliza objetos alternativos, ya que no necesita algunas cosas como la fecha de alta de la película en la BD. Para ello creamos ServiceMovieDto y ServiceSaleDto.

Un DTO (Data Transfer Protocol) es un objeto que se usa para transferir datos entre aplicaciones. Sirve para encapsular las diferencias con los objetos internos. La fecha se envía al cliente como un String.

|   **ServiceMovieDto**  |
|--------------|
| - movieId      |
| - title        | 
| - runtime      |
| - description  |
| - price        |
| + constructores        |
| + getters y setters        |

|   **ServiceSaleDto**  |
|--------------|
| - saleId      |
| - movieId       | 
| - expirationDate      |
| - movieUrl  |
| + constructores        |
| + getters y setters        |

### Capa de acceso a servicios
+ **ClientMovieService:** fachada con una interfaz para cada operación del servicio.
+ **ClientMovieServiceFactory:** factoría que permite construir una instancia de ClientMovieService sin que el llamador necesite conocer la clase que implementa el interfaz.

En conjunto sirven para que el cliente acceda a distintas implementaciones del servicio sin tener que recompilarlo.

En casos reales cada cliente usa sus propios objetos. En nuestro caso, el cliente necesita la duración en horas y minutos, por lo que se define un nuevo objeto:

|   **ClientMovieDto**  |
|--------------|
| - movieId      |
| - title        | 
| - runtimeHours     |
| - runtimeMinutes     |
| - description  |
| - price        |
| + constructores        |
| + getters y setters        |

### Capa interfaz de usuario
En MovieServiceClient definimos la interfaz por terminal con la que va a interactuar el usuario:
```
#Añadir una película:
MovieServiceClient -a <title> <hours> <minutes> <description> <price>

# Borrar una película:
MovieServiceClient -r <movieId>

# Actualizar una película:
MovieServiceClient -u <movieId> <title> <hours> <minutes> <description> <price>

# Buscar una película por palabras clave en el título:
MovieServiceClient -f <keywords>  

# Comprar una película:
MovieServiceClient -b <movieId> <userId> <creditCardNumber>

# Ver una película:
MovieServiceClient -g <saleId> 
```

