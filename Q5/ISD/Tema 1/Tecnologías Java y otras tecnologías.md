[[Tema 1-Introducción al desarrollo de aplicaciones empresariales]]

### Tecnologías estándar
+ **Java SE:** conjunto de especificaciones sobre como tiene que comportarse el compilador, la máquina virtual de Java... Dicho de mala manera, son los diferentes JDK.
+ **Java ME:** es similar a Java SE, pero para dispositivos con recursos limitados, como un Blue Ray, una televisión...
+ **Jakarta EE:** conjunto de APIs destinadas a la construcción de aplicaciones empresariales. Estas aplicaciones necesitan ser ejecutadas dentro de un servidor de aplicaciones. Algunos ejemplos son Jetty y Tomcat. Si se usan las APIs estándar es indiferente el servidor donde se ejecuten.

### Tecnologías por capas
##### Capa de acceso a datos
La tecnología que se usa en esta asignatura es JDBC (Java DataBase Conectivity). Posibilita el acceso a bases de datos relacionales. Permite lanzar consultas con Java. Existen otras a más alto nivel, como Hibernate.

##### Capa lógica de negocio
