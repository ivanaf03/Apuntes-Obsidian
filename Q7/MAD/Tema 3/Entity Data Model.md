[[Tema 3-Implementación de persistencia con ADO.NET Entity Framework]]

## Por qué usar un EDM?
Las bases de datos deben ser seguras, mantenibles, escalables y eficientes. Siguiendo todas las convenciones de la base de datos, se hace complejo para el desarrollador trabajar. Utilizando objetos de negocio el desarrollador puede evitar preocuparse de nombres de tablas, vistas, de la estructura, etc. Además, tampoco es necesario convertir los datos devueltos a objetos.

### Ventajas del EDM
Las ventajas del EDM son:
+ Genera las clases automáticamente a partir del modelo. 
+ Se encarga de toda la conectividad con la base de datos. 
+ Proporciona consultas simples sobre el modelo.
+ Realiza seguimiento de cambios.

## Creación del EDM
El modelo de datos se puede crear de 3 formas:
+ **DataBase First:** se crea la base de datos, con ella se genera el EDM y con este el código.
+ **Model First:** se crea el EDM y a partir de este se genera tanto el código como la BD.
+ **Code First:** no es recomendable. Crea la base de datos a partir del código.

### Cadena de conexión
> [!abstract] Definición de cadena de conexión
> La cadena de conexión es una configuración que define cómo una aplicación se conecta a una base de datos.

El crear el EDM se genera y se guarda en el archivo de configuración del proyecto. 

## Metadatos del modelo
A parte del modelo conceptual, también existen otros metadatos en EF: el mapping y el modelo lógico.

![[metadata_ef.png]]

El modelo y los metadatos se pueden actualizar mediante el asistente de actualización si se han realizado cambios en la base de datos.