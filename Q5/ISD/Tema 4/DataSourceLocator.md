[[Tema 4-Pruebas de integración de la capa modelo]]

## DataSources
MovieServiceTest tiene que crear un DataSource antes de poder invocar al servicio de la capa modelo. Sin embargo, cuando la capa Modelo se ejecuta dentro de un servidor de aplicaciones, es éste quien proporciona una implementación de un DataSource mediante un pool de conexiones.

Una aplicación instalada en un servidor de aplicaciones Java puede obtener referencias a objetos como DataSources mediante la API JNDI (Java Naming and Directory Interface).

```
InitialContext initialContext = new InitialContext();
DataSource dataSource = (DataSource) initialContext.lookup("java:comp/env/jdbc/ws-javaexamples-ds");
```

## DataSourceLocator
DataSourceLocator proporciona un mecanismo para gestionar fuentes de datos de manera centralizada, permitiendo agregar fuentes de datos y obtenerlas por su nombre, ya sea desde un mapa en memoria o buscándolas en el entorno JNDI si no están presentes en el mapa.

```
public class DataSourceLocator {  

    public static final String JNDI_PREFIX = "java:comp/env/jdbc/"; 
    private static Map<String, DataSource> dataSources = Collections.synchronizedMap(new HashMap());  

    private DataSourceLocator() {  
    }  
  
    public static void addDataSource(String name, DataSource dataSource) {  
        dataSources.put(name, dataSource);  
    }  
  
    public static DataSource getDataSource(String name) throws RuntimeException {  
        DataSource dataSource = (DataSource)dataSources.get(name);  
        if (dataSource == null) {  
            try {  
                InitialContext initialContext = new InitialContext();  
                dataSource = (DataSource)initialContext.lookup("java:comp/env/jdbc/" + name);  
                dataSources.put(name, dataSource);  
            } catch (Exception var3) {  
                throw new RuntimeException(var3);  
            }  
        }  
        return dataSource;  
    }  
}
```