[[Tema 2-Capa acceso a datos con Spring y JPA]]

# 1. Tecnologías
## 1.1. JPA e Hibernate
Es la Java Persistence API. Es un API de Java que coge entidades y las mapea a la base de datos. El paquete principal que usa es `jakarta.persistance`. Proporciona:
+ [>] Un conjunto de anotaciones para mapear entidades a una base de datos relacional.
+ [>] Un API para interactuar con la base de datos.

$\space$
Internamente utiliza JDBC. Usaremos Hibernate, una implementación de JPA.

## 1.2. Spring Data
Es una librería que permite implementar ágilmente DAOs sobre diferentes fuentes de datos, como bases de datos relaciones o NoSQL. Se suelen llamar repositorios a los DAOs.

# 2. Tablas
Hibernate permite crear automáticamente las tablas. Sobre las entidades se pueden utilizar anotaciones para indicar a que tablas se mapean.

También permite adaptarse a las tablas que ya existen. Es lo que se suele usar en proyectos reales.

JPA tiene tres formas de mapear entidades a tablas:
+ [>] Con anotaciones.
+ [>] En un fichero de configuración.
+ [>] Combinando las dos anteriores.

## 2.1. Tablas en PA Shop
En el ejemplo las tablas se crean en `backend/src/sql/1-MySQLCreateTables.sql`. Creamos las tablas de las bases de datos con:
```
cd backend
mvn sql:execute

mvn test //Para las tablas de test
```

Usaremos el mapeo mediante anotaciones.