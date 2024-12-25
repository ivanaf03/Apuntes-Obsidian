[[Tema 2-Automatización de procesos]]

## Cómo se gestionan los datos?
En la fase de desarrollo, los datos se almacenan en la base de datos embebida H2. Bonita permite la integración de un SGBD más potente externo. Tiene soporte para que en las propias tareas se lancen consultas a MySQL, Oracle o PostgreSQL.

### Tipos de datos
En Bonita las variables pueden ser de tipos básicos, como enteros o strings, objetos Java creados en el Business data model o importados de un .jar o variables XML. Los datos pueden ser:
+ **Business data model:** datos que se almacenan en la base de datos.
+ **Process variables:** datos que se utilizan a lo largo de la ejecución del proceso, sin necesidad de persistencia.
+ **Task variables:** datos locales y no persistentes que solo conoce la propia tarea que utiliza.

## Definición de datos
El modelo de datos se define mediante el asistente de Bonita. Este genera el código SQL de la base de datos y el código de Java necesario para la capa de acceso a datos. Se basa en los mapeadores objeto-relacionales, asociando clases Java a tablas de la base de datos directamente.

### Business objects
Los business objects están formados por el nombre de la clase Java asociada y por atributos. Cada atributo contiene su nombre y tipo de datos, longitud (no todos), restricciones de unique, not null y múltiples valores.

Además por defecto Bonita genera consultas de tipo `find`, `findBy` y `count`. Se pueden crear más consultas SQL sobre los atributos a mayores. También permite indicar índices sobre atributos.

Se pueden definir relaciones de agregación o composición entre objetos. Una composición es una relación fuerte donde si desaparecen todas las partes que componen a objeto, el objeto desaparece. En cambio, la agregación permite que el objeto exista sin las partes agregadas.

