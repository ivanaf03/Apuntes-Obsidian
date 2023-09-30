[[Tema 1-Introducción al desarrollo de aplicaciones empresariales]]

### Aplicaciones empresariales
Una aplicación empresarial es aquella que aborda necesidades críticas. 
  
Las aplicaciones de hoy en día no funcionan de forma aislada, por ejemplo, la aplicación del tiempo utiliza servicios de ubicación, un navegador web, el servicio del tiempo, etc. En estos casos se tiene muy poco control sobre los otros servicios, pueden ser de otras empresas y no es posible modificarlas.

##### Problemas
+ Necesita acceso a la red mediante tecnologías que utilizan sockets
+ La aplicación puede utilizar tecnologías diferentes a los servicios
+ La evolución entre las aplicaciones es totalmente independiente. Cuando ocurre esto es importante que la aplicación cliente siga en funcionamiento
  
##### Requisitos
+ **Alta disponibilidad:** el usuario no debe percibir que el servicio no funciona
+ **Escalabilidad:** capacidad de soportar más usuarios o carga al aumentar los recursos sin modificar el código
+ **Transaccionalidad:** cumple con las propiedades ACID (Atomicity, Consistency, Isolation, Durability)
+ **Seguridad:** los permisos de distribuye según el tipo de usuario