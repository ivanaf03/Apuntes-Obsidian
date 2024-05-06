[[Tema 2-Capa acceso a datos con Spring y JPA]]
$\space$
## 1.Tecnologías
Usaremos JPA e Hibernate y Spring Data para la capa de acceso a datos.
$\space$
### 1.1.JPA e Hibernate
JPA son las siglas de Java Persistence API. Es una API de Java que funciona como mapeador objeto-relacional, es decir, coge entidades y las mapea a la base de datos. El paquete principal que usa es `jakarta.persistance`. 

Usaremos Hibernate, que e una implementación de JPA. Realmente por dentro lo que usa esta API es JDBC.

Proporciona:
+ Anotaciones que permiten mapear entidades a una base de datos relacional.
+ Una API para interactuar con la BBDD. 
$\space$
### 1.2.Spring Data
Es una librería que permite implementar ágilmente DAOs sobre diferentes fuentes de datos, como bases de datos relaciones o NoSQL. En Spring se suelen llamar repositorios a los DAOs.
$\space$
## 2.Creación de tablas con Hibernate
Hibernate permite crear automáticamente las tablas. Sobre las entidades se pueden utilizar anotaciones para indicar a que tablas se mapean.

También permite adaptarse a las tablas que ya existen. Es lo que se suele usar en proyectos reales.
$\space$
### 2.1.Tipos de mapeo
Hibernate permite mapear las entidades a tablas de tres formas.
+ Con anotaciones. Es la que usaremos.
+ En un fichero de configuración.
+ Combinando las dos anteriores.
$\space$
### 2.2.Creación de tablas
En PA Shop las tablas se crean en el script `backend/src/sql/1-MySQLCreateTables.sql`. Para crearlas:

```
cd backend
mvn sql:execute //tablas PA

mvn test //tablas PATEST
```

