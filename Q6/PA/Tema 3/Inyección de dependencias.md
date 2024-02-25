[[Tema 3-Capa lógica de negocio con Spring]]

# 1.Servicios locales
Los servicios locales usan los DAOs y el servicio interno `PermissionChecker`. La implementación de cada servicio debe poder obtener una instancia de cada DAO y del servicio interno sin conocer las clases de implementación.

Se podría definir una factoría para cada DAO, pero en una situación real habría demasiadas factorías. Los frameworks utilizan el principio de inyección de dependencias.

Consiste en tener un contenedor de objetos que crea los objetos, que denomina `beans`, y les inyecta las referencias a los objetos de los que dependen al arranque de la aplicación. Se puede hacer mediante:
+ [>] Ficheros
+ [>] Anotaciones

## 1.1.Inyección de dependencias mediante anotaciones
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

Las anotaciones que usa son:
+ [>] *@Repository:* clases DAO en caso de que los DAOs no sean implementados por Spring Data. No es el caso.
+ [>]  *@Service:* clases de servicios locales.
+ [>] *@Autowired:*  inyecta un bean que implementa la interfaz del atributo. Si hay más de un bean que implementa esa interfaz es necesario especificarlo con otras anotaciones.

### 1.1.1.Beans
Los beans son `singletons`. Son una instancia única de un DAO o servicio local. Al arrancar el backend el contenedor de objetos de Spring crea una instancia de cada `@Repository` y `@Service`, estén no no anotadas explicitamente. Para cada bean inspecciona los atributos anotados con `@Autowired` y crea un bean.