[[Xestión de procesos de negocio]]

El problema de tener una arquitectura centralizada es que es muy extraño meter funcionalidades muy diferentes en un mismo sistema. Debido a eso, entre otras cosas, se paso a crear sistemas que cubran varias áreas de trabajo diferentes.

Como integrar sistemas:
+ Servicios web (REST, SOAP)
+ BD compartidas
+ Ficheros binarios
+ Objetos distribuidos (CORBA)

Patas SOA:
+ Servicios
+ Infraestructura
+ Políticas

Se suele usar API first con YAML.

Tipos de servicios en función del alcance:
+ Básicos
+ Compuestos
+ De proceso
+ Microservicios

Cambiar una API hace que se cambie todo lo que implementa esa API, por tanto, no debería hacerse nunca o, en caso de hacerlo, tener mucho cuidado. 

Conexiones físicas: conexión de red entre cliente y servidor. Puede ser:
+ Punto a punto: Si B tiene un API, A hace la llamada y espera a la respuesta.

Estilo de comunicación: 
+ Síncrona: Esperas la respuesta. Si peta el timeout se pueden implementar cosas como políticas de reintentos, por ejemplo, con un middleware. Aporta tolerancia a fallos y gestión de prioridades. Funciona como un proxy.
+ Asíncrona: Haces la petición y quedas esperando. Se puede hacer mediante requests y callbacks.

ESB (Enterprise Service Bus): hace comunicaciones punto a punto. A hace una petición al mediador, este la hace a B, B responde al mediador y el mediador a A. Una forma de mejorar esto es con el Publisher Subscriber. A hace un pedido al ESB y es este quien sabe a quien se lo tiene que comunicar. 

El Observador es el ESB y el Publisher es un observable.

En el ESB se configuran el adaptador, los publicador y los suscriptores.

Control centralizado: orquestación
Control distribuido: coreografía

Desplegar de forma simultánea más acoplados.

