[[Tema 3-Capa lógica de negocio con Spring]]
$\space$
## 1.Servicios locales
Los servicios locales necesitan los DAOs y el servicio `PermissionChecker` para su implementación. Para implementar cada servicio se necesita una instancia de cada DAO y de los servicios internos sin conocer las clases de su implementación.

Una forma es utilizando el patrón factoría para cada DAO y otra para el `PermissionChecker`. Sin embargo, puede haber muchos DAOs en un caso real. Para ello los frameworks suelen utilizar la inyección de dependencias.

El principio de inyección de dependencias es un patrón de diseño en el que los componentes de un sistema no crean directamente las otras partes de las que dependen, sino que se les pasan desde el exterior.
$\space$
### 1.1.Inyección de dependencias en Spring
Spring tiene un contenedor de objetos que se encarga de crearlos e inyectarles las referencias de los objetos de los que dependen al arrancar la aplicación. Estos se llaman beans. Se usa la inyección de dependencias en los DAO y en los servicios locales.

Spring permite hacer inyección de dependencias de dos formas:
+ Mediante anotaciones
+ En ficheros de configuración
$\space$
#### 1.1.1.Uso de anotaciones

```java
@Service  
@Transactional  
public class ShoppingServiceImpl implements ShoppingService {  
      
    @Autowired  
    private PermissionChecker permissionChecker;  
      
    @Autowired  
    private ProductDao productDao;  
      
    @Autowired  
    private ShoppingCartItemDao shoppingCartItemDao;
...
}
```

Las anotaciones que se usan son:
+ **@Repository:** clases DAO en caso de que los DAOs no sean implementados por Spring Data. En nuestro caso si los implementa.
+ **@Service:** servicio local.
+ **@Autowired:** inyecta un bean que implementa la interfaz del atributo. Si más de un bean implementa esa interfaz lanza una `NoUniqueBeanDefinitionException`.
$\space$
#### 1.1.1.Beans
Un bean es un singleton que forma una instancia única de cada servicio local o DAO. Al arrancar la aplicación el contenedor de Spring busca las clases anotadas con `@Repository` o con `@Service` y crea una instancia de ellas. Para cada atributo anotado con `@Autowired` crea un bean.

