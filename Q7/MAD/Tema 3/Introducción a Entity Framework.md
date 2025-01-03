[[Tema 3-Implementación de persistencia con ADO.NET Entity Framework]]

## Programación contra un modelo conceptual
Entity Framework es una librería cuya idea es evitar pensar en la estructura de la base de datos. El acceso a datos y el almacenamiento se hacen contra el modelo conceptual que crea, el EDM (Entity Data Model).

Con tecnologías más antiguas era necesario escribir código de acceso a datos y transformar los datos en objetos del dominio. Con Entity Framework se recuperan directamente los objetos del dominio y se persisten los cambios en base de datos cuando es necesario.

### Entidades del modelo conceptual
Las "tablas" que contiene un EDM se llaman entidades, las clases que se generan a partir de estas clases de entidad y las instancias objetos de entidad. Tienen propiedades, pero no comportamiento, excepto los métodos de seguimiento de cambios y `equals()`, `getHashCode()` y `toString()`.

![[entidades_edm.png]]

## Características de EF
Entity Framework se caracteriza por:
+ Permite una amplia serie de proveedores de bases de datos, aunque se suele utilizar SQLServer.
+ Proporciona varias APIs y herramientas.

### Metadatos
Almacena el modelo conceptual en un XML. Este fichero contiene una definición del esquema de la base de datos y de las relaciones del modelo conceptual. Mediante estos metadatos realiza las transformaciones necesarias para pasar de modelo a base de datos y viceversa.

### Herramientas de diseño
EF proporciona una herramienta que permite trabajar de forma gráfica con el modelo de entidades sin tener que manipular el XML. También trae un generador de código que genera clases a partir del modelo.

### Object services
Los objetos de servicio son una capa de servicios que proporcionan la clase `EntityObject`, que permite trabajar con `DbContext` para gestionar la materialización de objetos, la serialización, los cambios que se hacen sobre estos y la transformación de consultas Linq a SQL.

### Seguimiento de cambios
También lo hacen los objetos de servicio una vez se instancia un objeto entidad. Utilizan el seguimiento para poder crear, actualizar o borrar los datos de los objetos.

### Gestión de relaciones y claves foráneas
EF convierte las relaciones en propiedades de navegación con lazy loading. 

### Entity Client
Funciona como un puente entre `DbContext` o los objetos de servicio y la base de datos. Permite realizar consultas, ejecutar comandos o recuperar resultados. La diferencia es que trabajando a tan bajo nivel de pueden obtener los resultados en forma de tablas en lugar de obtener objetos directamente.

### Permite evitar el uso de DataSets y DataReaders
En proyectos a alto nivel, no es necesario trabajar a tan bajo nivel.