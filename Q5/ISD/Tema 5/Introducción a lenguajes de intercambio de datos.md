[[Tema 5-Lenguajes de intercambio de datos XML y JSON]]

### Aplicaciones remotas
La capa modelo es un servicio que puede ser utilizado por aplicaciones remotas. Estas se caracterizan por:
+ Pueden residir en otras máquinas o acceder a la capa modelo a través de Internet.
+ Pueden estar escritas en cualquier lenguaje de programación, no tiene que ser el mismo que el de la capa modelo
+ Pueden usar otras bases de datos o aplicaciones además de la nuestra.

Utilizan lenguajes como XML, JSON y YAML como lenguajes de formato de datos.

##### Ejemplo: un portal externo desea ofrecer el servicio de búsqueda y visión de películas
Una opción sería que nuestro servicio tenga una URL a la que es posible pasarle parámetros de las keywords de búsqueda. Por ejemplo: http://.../findmovies/?keywords=dark.

### Utilidades
+ Intercambio de datos entre aplicaciones heterogéneas
+ Generación de vistas a partir de documentos de datos (pdf, html, etc)
+ Bases de datos
+ Configuración de aplicaciones (pom.xml de maven)