[[Tema 8-Proceso unificado]]

## Qué es la vista 4+1?
Es una propuesta que organiza la arquitectura de un sistema en 5 vistas:
+ **Lógica:** define qué hace el sistema y cómo interactúan sus componentes.
+ **Desarrollo:** define cómo se organiza desde el punto de vista de los desarrolladores.
+ **Proceso:** define cómo se comporta en tiempo de ejecución.
+ **Física:** define como se despliega en hardware y redes.
+ **Escenarios:** es la vista +1. Son los casos de uso o escenarios que validan las otras vistas.

Cada una de las vistas es preocupación de ciertas personas, como clientes desarrolladores, arquitectos...

### Vista de escenarios
> [!abstract] Definición de escenario
> Un escenario es una secuencia de interacciones entre objetos y procesos.

Los escenarios son un grupo de casos de uso que se utilizan para validar el diseño de la arquitectura. También sirven como punto de partida para pruebas de un prototipo de arquitectura.

### Vista lógica
Esta vista define los componentes principales del sistema. Se basa en los casos de uso. Para las representaciones se utilizan los diagramas de clases, de comunicación y de secuencia.

### Vista de desarrollo
Muestra como se organiza el software desde el punto de vista de los desarrolladores. Describe los módulos, paquetes y componentes del sistema. También se conoce como vista de implementación. Para las representaciones se utilizan diagramas de componentes o de paquetes.

Los diagramas de componentes muestran las interacciones entre los componentes del sistema. Permiten visualizar la arquitectura de alto nivel, organizar las responsabilidades del equipo y apoyar el desarrollo iterativo.

Los componentes se unen mediante:
+ **Sockets:** indica que un componente necesita un servicio o información. Representa al componente dependiente o solicitante.
+ **Lollipop:** indica que un componente provee de un servicio o funcionalidad. Representa al proveedor.

![[socket_lollipop.png]]

Los componentes se conectan mediante interfaces. Pueden interactuar de dos formas:
+ **Pull:** el socket solicita servicios al componente proveedor.
+ **Push:** un componente envía automáticamente datos o eventos al otro componente.

### Vista de proceso
Trata los aspectos dinámicos del sistema, explicando los procesos y cómo se comunican. Se enfoca en el comportamiento en tiempo de ejecución. Considera concurrencia, escalabilidad, rendimiento y otros requisitos no funcionales. Se representa mediante diagramas de actividad. 

![[diagrama_actividad.png]]

### Vista física o de despliegue
Describe el sistema desde el punto de vista de un ingeniero de sistemas. Esta muy relacionado con la capa física del software. Para representarla se utiliza el diagrama de despliegue.

![[diagram_despliegue.png]]