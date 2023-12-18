[[Tema 6-Diseño e implementación de servicios web REST]]

## Protocolo REST
### Recursos
/movies es un recurso colección. POST añade una nueva película y GET lista todas las películas. 

/movies/id es un recurso individual (cada película). PUT modifica la película y DELETE borra la película.

/sales es un recurso colección. POST añade una nueva venta.

/sales/id es un recursos individual (cada venta). GET obtiene información de la venta.

### Errores
+ 400 Bad Request para InputValidationException
+ 404 Not Found para InstanceNotFoundException
+ 410 Gone para SaleExpirationException
+ 403 Forbidden para MovieNotRemovableException
+ 500 Internal Error

Normalmente un mismo código de error estará asociado a varias excepciones.

## Consideraciones de diseño REST
### Creación de recursos con POST
+ La URL en la cabecera Location permite al cliente conocer la URL del nuevo recurso creado para referirse a él más tarde. 
+ Usar una cabecera estándar permite proporcionar semántica para cualquier intermediario y cliente, aunque no conozcan los formatos de nuestro servicio
+ Devolver completo el nuevo recurso creado en el cuerpo es útil si creemos que el cliente va a utilizarlo de inmediato (ahorra al cliente una petición HTTP). A veces renta enviar solo el id.

### Overloaded POST
El overloaded POST se utiliza cuando se manejan operaciones que no encajan con las operaciones básicas CRUD. Por ejemplo, podemos marcar una película como destacada así:
```
POST http://XXX/ws-movies-service/movies/{id}/highlight
```

## Aplicaciones web Jakarta EE
En Jakarta EE las aplicaciones web se instalan en servidores de aplicaciones. Cualquier aplicación Jakarta EE puede instalarse en un servidor. Se distribuyen en ficheros war. (web archive).

Las APIs de programación Web Java no están pensadas para devolver sólo HTML/XHTML, sino cualquier tipo de información sobre HTTP. Por ello se pueden usar para implementar servicios web. Para ello usamos la API de Servlets.

### Servlets
Un servlet es una clase asociada a una o varias URLs. Extiende HttpServlet y redefine los métodos doXXX. Cuando el server recibe una petición sobre ella invoca al servlet. Este se encarga de:
+ Accede al contenido de la petición.
+ Ejecuta el código que le permite obtener la respuesta.
+ Codifica la respuesta en el formato deseado.

Es un modelo multithread. Cada vez que el servidor de aplicaciones recibe una petición dirigida a un servlet, la petición se procesa en un thread independiente.

La clase ServletRequest:
+ **getParameter:** permite obtener el valor de un parámetro univaluado.
+ **getParameterValues:** permite obtener el valor de un parámetro multivaluado.
+ **getInputStream:** permite leer el cuerpo de la petición.

La clase HttpServerRequest:
+ **getPathInfo:** fragmento del path de la petición a partir de la URL asociada al Servlet (y siempre empieza por '/'). Por ejemplo, "/movies/123" devuelve "/123".
+ **getRequestURL:** devuelve la URL completa que utilizó el cliente para realizar la petición sin incluir parámetros.

La clase ServletResponse:
+ **setContentType:** especifica el tipo de contenido de la respuesta.
+ **getOutputStream:** permite escribir el cuerpo de la respuesta.

La clase HttpServletResponse:
+ **setStatus:** especifica el código de estado de la respuesta.
+ **setHeader:** añade una cabecera con el nombre y el valor especificados a la respuesta.

La clase ServletUtils:
+ **writeServiceResponse:** escribe una respuesta HTTP.
+ **normalizePath:** recibe un String y devuelve otro String igual al recibido quitándole el carácter / en caso de que finalice con él.
+ **getMandatoryParameter o getMandatoryParameterAsLong):** obtiene el valor del parámetro indicado o lanza una InputValidationException si el parámetro no viene en la petición.
+ **checkEmptyPath:** comprueba si el path de una petición HTTP es vacío, nulo o está compuesto solo por '/' y en caso negativo lanza una InputValidationException.
+ **getIdFromPath:** obtiene un identificador de tipo Long a partir del path de una petición HTTP que siga el formato '/'. En caso de no poder obtener el identificador lanza una InputValidationException.

Para facilitar la implementación de Servlets usamos RestHttpServletTemplate.

Los Servlets no tratan las RuntimeExceptions. Cuando ocurren devuelven una excepción 500 Internal Server Error.

### Empaquetamiento de una aplicación web
```
jar cvf aplicacionWeb.war directorio
```
Este comando funciona similar al comando tar de Unix. Los ficheros .war son generados por Maven. Están formados por ficheros .class que conforman la aplicación, ficheros .jar de librerías que usa la aplicación y el fichero web.xml con la configuración estándar de la aplicación. 

Estos ficheros se instalan en los servidores de aplicaciones Jakarta EE.

## HttpClient
HttpClient es un framework que se usa en la capa de acceso a servicios. Dentro de este usaremos la Fluent API.

La clase Request representa una petición HTTP:
+ **bodyStream:** permite asignar un contenido cualquiera al cuerpo de la petición.
+ **execute:** envía la petición y devuelve un objeto Response que representa la respuesta a la petición.

La clase ClassicHttpResponse representa una respuesta HTTP.

## Validación de documentos
Tanto los clientes como el servicio del ejemplo comprueban que el JSON está bien formado con Jackson de forma automática. Pero ni los clientes ni el servicio comprueban que el documento es válido. Aunque se hacen comprobaciones por ejemplo, en la capa modelo, para ver si los parámetros son válidos.

### Ventajas
+ Eficiencia.
+ Evolución temporal. Es posible extender el JSON/XML del protocolo sin que dejen de funcionar clientes y/o servicios.