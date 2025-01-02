[[Tema 8-Proceso unificado]]

## Ciclos del PUD
El PUD se divide en una serie de ciclos que constituyen la vida de un sistema. Cada ciclo finaliza con una versión entregable para los clientes. Están formados por las fases de: inicio, elaboración, construcción y transición. A su vez, cada una de las fases se divide en iteraciones.

### Producto en las fases del ciclo
Cada fase produce una nueva versión del sistema. El producto incluye código, documentación, componentes ejecutables, etc. 

Al terminar, se genera el producto final. Se diferencia de las versiones en que se debe ajustar a las necesidades técnicas y arquitectónicas, a demás de a las de los usuarios. Debe contener las especificaciones funcionales y no funcionales y todos los modelos de arquitectura y documentación necesarios asociados. Estos elementos ayudan a mantener el sistema.

Se puede representar mediante:
+ Modelo de casos de uso, detallando las interacciones.
+ Modelo de análisis, detallando las funcionalidades.
+ Modelo de diseño, describiendo la estructura.
+ Representación de la arquitectura.
+ Contextualización del dominio.
+ Modelo de implementación, describiendo los componentes y sus relaciones.
+ Modelo de despliegue, que especifica nodos físicos.
+ Modelo de pruebas.

## Fases de cada ciclo
Durante cada fase se pasa por todas las actividades del desarrollo software, en mayor o menor medida.

![[puds_ciclo.png]]

### Fase de inicio
La fase de inicio busca tener una idea inicial del producto y de la viabilidad en el negocio. Se detallan:
+ Funciones principales del sistema.
+ Arquitectura provisional.
+ Plan del proyecto y estimación de riesgos.

### Fase de elaboración
Se pasa de la versión inicial a una arquitectura estable y viable. Se especifican la mayoría de casos de uso y se definen los diseños que refinarán la arquitectura. 

La idea de esta fase es comprobar la viabilidad de la arquitectura mediante prototipos y componentes críticos. Se refinan modelos los modelos para hacerlos escalables y alineados con los requisitos. Produce como resultado la línea base de la arquitectura.

### Fase de construcción
Esta fase se centra en desarrollar el sistema al completo en función de la línea base de arquitectura. Se refina y se expande la arquitectura inicial para incorporar las funcionalidades completas. Se comprueba que el producto vaya alineado a los requisitos.

Se hacen el diseño, la codificación, las pruebas y la integración. Al final de la integración se genera un producto listo para ser probado en el entorno del cliente.

### Fase de transición
Se prepara el producto para la entrega al usuario final. Se realizan pruebas beta con un grupo limitado de usuarios, se recopilan defectos y fallos y se incorporan mejoras para la versión final.

En esta fase se forman a los usuarios finales y equipos técnicos, se da soporte, se prepara la documentación y la distribución y se planifican las actualizaciones. Al final de la fase el producto debe estar completo y en producción.