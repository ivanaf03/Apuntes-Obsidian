[[Tema 3-Diseño e implementación de la capa modelo]]

### Movies
Movies en un ejemplo que proporciona:
+ **Capa modelo:** operaciones para gestionar información sobre películas y comprarlas
+ **Capas de servicios RESTful y Thift:** tratan la lógica de negocio mediante una interfaz más adaptada a las necesidades de los clientes
+ **Un cliente:** línea de comandos

##### Capa modelo
La capa modelo permite los siguientes casos de uso:
+ Añadir películas
+ Actualizar películas
+ Eliminar películas sin compras
+ Buscar películas por clave
+ Buscar películas por palabras clave del título
+ Comprar películas

### Principios de diseño
La capa modelo ofrece una API con las siguientes características:
+ Permite invocar cada caso de uso de forma sencilla. Esto facilita el trabajo del desarrollador de la capa superior.
+ Oculta detalles de implementación. Tiene que poder modificarse sin afectar a la capa superior.

### Método de desarrollo
1. [[Modelado de entidades]]
2. [[Definición de API modelo]]
3. [[Gestión de la persistencia]]
4. [[Implementación de los casos de uso]]
5. [[Tema 4-Pruebas de integración de la capa modelo|Pruebas de integración]]
