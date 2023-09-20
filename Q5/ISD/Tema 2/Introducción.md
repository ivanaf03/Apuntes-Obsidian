[[Tema 2-JDBC Conectividad de bases de datos con java]]

### Drivers
Java tiene mecanismos para acceder a bases de datos relacionales. La API de Java que se encarga de esto se llama JDBC. Los paquetes con los que se trabajan son java.sql y javax.sql.

Para poder conectarse a la base de datos y lanzar consultas es necesario un driver. Los drivers son ficheros que contienen ficheros .jar con la implementación de las librerías.

Esto nos permite que si cambiamos de bases de datos, no es necesario cambiar el código, sino cambiar el driver. El problema es que las bases de datos utilizan diferentes dialectos de SQL.

Es importante recordar que en JDBC los índices empiezan en 1, no en 0 como en Java.