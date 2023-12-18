[[Tema 1-Introducción al desarrollo de aplicaciones empresariales]]

## Las propiedades ACID
+ **Atomicity:** Atomicidad. Capacidad de una transacción para ser tratada como una unidad completa e indivisible.
+ **Consistency:** Consistencia. Capacidad de mantener la integridad de los datos y de la aplicación.
+ **Isolation:** Aislamiento. Capacidad de una operación para ejecutarse de manera aislada, sin interferencias de otras operaciones concurrentes.
+ **Durability**: Durabilidad. Capacidad de que los resultados de una operación persistan, incluso en el caso de fallos del sistema.

## Las aplicaciones empresariales
Una aplicación empresarial es aquella que aborda necesidades críticas. Las aplicaciones hoy en día no funcionan de forma aislada. Por ejemplo, la aplicación del tiempo utiliza servicios como la ubicación, un navegador web, el servicio del tiempo, etc.

En estos casos se tiene muy poco control sobre los otros servicios. Por ejemplo, pueden ser de otras empresas y no es posible modificarlos.

### Problemas
+ Necesita acceso a la red.
+ La aplicación puede utilizar tecnologías diferentes a los servicios.
+ La evolución entre las aplicaciones es totalmente independiente.
  
### Requisitos
+ **Alta disponibilidad:** el usuario no debe percibir que el servicio no funciona.
+ **Escalabilidad:** necesita capacidad de soportar más usuarios o carga al aumentar los recursos sin tener que modificar el código.
+ **Transaccionalidad:** cumple con las propiedades ACID (Atomicity, Consistency, Isolation, Durability)
+ **Seguridad:** los permisos se distribuyen según el tipo de usuario.