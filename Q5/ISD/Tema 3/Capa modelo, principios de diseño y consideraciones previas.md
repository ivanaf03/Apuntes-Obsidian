[[Tema 3-Diseño e implementación de la capa modelo]]

## Ejemplo: Movies
Movies en un ejemplo que proporciona:
+ **Capa modelo:** operaciones para gestionar información sobre películas y comprarlas.
+ **Capas de servicios RESTful y Thift:** tratan la lógica de negocio mediante una interfaz más adaptada a las necesidades de los clientes.
+ **Un cliente:** línea de comandos.

### Capa modelo
La capa modelo permite los siguientes casos de uso:
+ Añadir películas
+ Actualizar películas
+ Eliminar películas sin compras
+ Buscar películas por clave
+ Buscar películas por palabras clave del título
+ Comprar películas

Está formada por dos entidades: la película y la venta.
```
Película(ID, título, duración, descripción, precio, fecha_de_alta)
Venta(ID, ID_película, ID_usuario, fecha_de_expiración, número_de_tarjeta, precio_película, URL_streaming, fecha_de_venta)
```

## Principios de diseño
La capa modelo ofrece una API con las siguientes características:
+ Permite invocar cada caso de uso de forma sencilla. Esto facilita el trabajo del desarrollador de la capa superior.
+ Oculta detalles de implementación. Tiene que poder modificarse sin afectar a la capa superior.

## Consideraciones previas
### Errores lógicos
Son errores del usuario final. Por ejemplo, un mal formato de entrada, actualizar una película que no está en la BD... La capa modelo notifica esto lanzando excepciones de tipos checked, que son las excepciones hijas de Exception. Se capturan en la interfaz de usuario y se muestran mensajes de error para que el usuario corrija los datos. Por ejemplo, el Movies:
+ **InstanceNotFoundException:** se intenta hacer algo sobre un objeto que no existe.
+ **InputValidationException:** se ha proporcionado una información de entrada en formato erróneo.

### Errores graves
Representan un error en la infraestructura, como una caída en la BD, un acceso a una tabla inexistente... En Movies se capturan con un RuntimeException y se altera al usuario diciéndole que ha ocurrido un error externo.

## Método de desarrollo
1. [[Modelado de entidades]]
2. [[Definición de API modelo]]
3. [[Gestión de la persistencia]]
4. [[Implementación de los casos de uso]]
5. [[Tema 4-Pruebas de integración de la capa modelo|Pruebas de integración]]