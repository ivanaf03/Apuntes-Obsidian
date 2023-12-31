[[Tema 7-Diseño e implementación de Servicios RPC]]

## Otras tecnologías
### SOAP
Es un protocolo (estandarizado por W3C) que permite invocar servicios remotos intercambiando mensajes en formato XML. Los mensajes SOAP se envían encapsulados en otros protocolos de nivel de aplicación (HTTP es el usado habitualmente). 

Utiliza WSDL como lenguaje de definición de la interfaz del servicio. Permite especificar en XML la interfaz de un servicio.

### gRPC
Permite invocar servicios remotos usando un protocolo binario sobre HTTP/2 para el intercambio de mensajes. Utiliza Protocol Buffers como lenguaje de definición de la interfaz del servicio.

## REST vs RPC
En el modelo RPC no existe el concepto de identificador global, los identificadores son locales a cada servicio. Además no se soportan intermediaros transparentes, ya que la semántica de las operaciones es propia de cada servicio. No soporta hipermedia.

En algunos frameworks RPC (sobre todo en las implementaciones más antiguas) el acoplamiento del cliente con el servicio es más elevado. Con las tecnologías usadas habitualmente con REST, puede conseguirse fácilmente que ciertos cambios no nos afecten. Con RPC modernos también se puede.

En RPC modelar un servicio es muy simple. El uso de operaciones ad-hoc, stubs/skeletons es más amigable al programador. Con REST manejamos peticiones HTTP y parsing/generación de JSON/XML. 