[[Tema 6-Diseño e implementación de servicios web REST]]

## ¿Qué es REST?
REST son las siglas de REpresentational State Transfer. Es un estilo arquitectónico que sirve para construir aplicaciones distribuidas basado en las características de la Web. Los servicios REST que siguen fielmente todos los requisitos se llaman RESTful.

Es independiente de la tecnología, pero se suele implementar usando HTTP y un lenguaje de intercambio como JSON o XML. 

## HTTP
HTTP son las siglas de HyperText Tranfer Protocol. Es el protocolo cliente-servidor utilizado en la Web. Se utiliza para transferir todo tipo de contenido, desde páginas HTML hasta imágenes. Sigue un esquema petición/respuesta.

### Peticiones HTTP
El protocolo HTTP utiliza las URL como identificadores globales de recursos. Una petición HTTP está formada por:
+ **URL:** identifica al recurso sobre el que se actúa.
+ **Método de acceso:** GET, POST, PUT, etc. Especifican que acción se realiza sobre el recurso.
+ **Cabeceras:** metainformación de la petición (por ejemplo, información de autenticación).
+ **Cuerpo:** algunos métodos de acceso tienen un mensaje con cuerpo.

### Métodos de acceso
+ **GET:** solicita una representación del recurso solicitado. Es seguro y de solo lectura. No hay que esperar cambios en el servidor ni produce cambios. Se pueden realizar consultas utilizando el & para separar los pares campo=valor. Por ejemplo: http://www.bookshop.com/search?tit=Java&author=John+Smith
+ **PUT:** carga un recurso en el servidor. No tenía por que existir previamente. No es seguro.
+ **DELETE:** elimina un recurso. Tampoco es seguro.
+ **POST:** envía datos a un recurso para que los procese. Tampoco es seguro.

La principal diferencia entre PUT y POST es que PUT es idempotente, es decir, el sistema no se ve afectado por la repetición de la misma solicitud, y el estado es el mismo que después de una sola solicitud. Por ejemplo, dos peticiones POST idénticas de creación de usuario crearán dos usuarios.

### Respuestas HTTP
Las respuestas HTTP contienen:
+ **Códigos de error:** como 200 ok, 201 created, 400 bad request, 403 forbidden, 404 not found, 500 internal error...
+ **Cabeceras:** metainformación de la respuesta.
+ **Cuerpo del mensaje:** a veces viene vacío. En las peticiones GET es la representación del recurso solicitado.

## Servicios REST
Los servicios web REST tienen una estructura muy similar a la web. Lo que los diferencia es que se accede a información estructurada en lugar de a páginas HTML. Los servicios web REST se consideran autónomos entre sí y pueden referenciarse mediante links.

### Servicios stateless
Los clientes invocan URLs para acceder a los recursos. El servidor no guarda información de estado para cada cliente. HTTP es un servicio sin estado. Cada petición de un cliente debe contener toda la información necesaria para que el servidor la responda.

Las ventajas de este tipo de servicios son:
+ Facilidad para replicar el servicio en múltiples máquinas mediante un balanceador de carga.
+ El servidor no necesita reservar recursos para cada sesión.
+ Mejora la escalabilidad.

Lo único malo es que a veces es necesario enviar información adicional en las peticiones.

### Recursos y representaciones
Las aplicaciones REST están compuestas por recursos (entidades persistentes). Pueden ser colecciones o individuales. Cada recurso tiene asociado un identificador único y global, generalmente una URL.

Al invocar la URL mediante un GET se obtiene una representación del recurso. Los recursos de tipo colección suelen devolver una lista de los elementos, con información resumida y enlaces a la información completa. Los recursos individuales suelen devolver datos del elemento. La representación de estos puede cambiarse.

### Interfaces uniformes
Los servicios REST tienen una serie de operaciones que siempre deben ser las mismas y funcionan igual en todos los servicios. Los tipos de respuesta también están estandarizados.

Se utiliza HTTP:
+ **GET:** acceso a representaciones.
+ **PUT:** reemplaza la representación o crea recursos individuales.
+ **DELETE:** borra un recurso.
+ **POST:** crear un recurso en una colección. También puede usarse para otras operaciones.

Los códigos de respuesta también son los de HTTP. Debemos distinguir entre códigos de error:
+ **Permanentes:** 400, 403, 410...
+ **Temporales:** 404, 500...

El uso de interfaces uniformes permite que haya intermediarios entre el cliente y el servicio. Por ejemplo, servidores caché internos. Estos sirven una copia del recurso solicitado si la tienen y, si no, invocan al sitio web/servicio real. Otros servicios intermediarios pueden ser proxies, traductores de formatos...