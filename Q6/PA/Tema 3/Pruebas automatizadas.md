[[Tema 3-Capa lógica de negocio con Spring]]

# 1.Tests
Cada caso de prueba se ejecutará en un método `@Test`. Los casos de prueba deben ser independientes entre sí. Utilizan DAOs desde las clases de prueba cuando es necesario. Utilizan dos bases de datos:
+ [>] *pa:* para probar la aplicación como desarrollador.
+ [>] *patest:* para ejecutar las pruebas automatizadas.

## 1.1.Spring test
Usaremos la librería spring-test de Spring Boot. Se usa la anotación `@SpringBootTest` a nivel de clase. Permite:
+ [>] Ejecutar las pruebas con JUnit5.
+ [>] Usar las características de Spring Boot.
+ [>] Inyectar beans en las clases de pruebas.

```java
@SpringBootTest
@ActiveProfiles("test")
@Transactional
public class <<Service>>Test {
    @Autowired
    private <<Service>> service;
    
    @Autowired
    private <<Dao>> dao;
    
    @Test
    public void test<<UseCase>>() throws ... {
        ...
        assertXxx(...);
    }
    ...
}
```

Además usamos `@Transactional` a nivel de clase. Cada caso de prueba se ejecuta en una transacción. Por defecto los métodos transaccionales terminan con `rollback`. Esto sirve para deshacer automáticamente los cambios que se hicieron en la base de datos sin tener que hacerlo en cada caso de prueba.

## 1.2.Ejemplo: ShoppingServiceTest
```java
@SpringBootTest  
@ActiveProfiles("test")  
@Transactional  
public class ShoppingServiceTest {  
      
    private final Long NON_EXISTENT_ID = Long.valueOf(-1);  
      
    @Autowired  
    private UserService userService;  
      
    @Autowired  
    private ShoppingService shoppingService;  
      
    @Autowired  
    private CategoryDao categoryDao;  
      
    @Autowired  
    private ProductDao productDao;

-...

	private User signUpUser(String userName) {  
	      
	    User user = new User(userName, "password", "firstName", "lastName", userName + "@" + userName + ".com");  
	      
	    try {  
	       userService.signUp(user);  
	    } catch (DuplicateInstanceException e) {  
	       throw new RuntimeException(e);  
	    }  
	      
	    return user;  
	      
	}

	private Category addCategory(String name) {  
	    return categoryDao.save(new Category(name));  
	}  
	  
	private Product addProduct(String name, Category category) {  
	    return productDao.save(new Product(name, "description", new BigDecimal(1), category));  
	}  
	  
	private Product addProduct(String name) {  
	    return addProduct(name, addCategory("category"));  
	}  
	  
	private Order addOrder(User user, Product product, LocalDateTime date) {  
	  
	    String postalAddress = "Postal Address";  
	    String postalCode = "12345";  
	    Order order = new Order(user, date, postalAddress, postalCode);  
	    OrderItem item = new OrderItem(product, product.getPrice(), 1);  
	      
	    orderDao.save(order);  
	    order.addItem(item);  
	    orderItemDao.save(item);  
	      
	    return order;  
	      
	}

...

	@Test  
	public void testBuyAndFindOrder() throws InstanceNotFoundException, PermissionException, MaxQuantityExceededException,  
	    MaxItemsExceededException, EmptyShoppingCartException {  
	      
	    User user = signUpUser("user");  
	    Product product1 = addProduct("product1");  
	    Product product2 = addProduct("product2", product1.getCategory());  
	    int quantity1 = 1;  
	    int quantity2 = 2;  
	    String postalAddress = "Postal Address";  
	    String postalCode = "12345";  
	            
	    shoppingService.addToShoppingCart(user.getId(), user.getShoppingCart().getId(), product1.getId(), quantity1);  
	    shoppingService.addToShoppingCart(user.getId(), user.getShoppingCart().getId(), product2.getId(), quantity2);  
	      
	    Order order = shoppingService.buy(user.getId(), user.getShoppingCart().getId(), postalAddress, postalCode);      
	    Order foundOrder = shoppingService.findOrder(user.getId(), order.getId());  
	      
	    assertEquals(order, foundOrder);  
	    assertEquals(user, order.getUser());  
	    assertEquals(postalAddress, order.getPostalAddress());  
	    assertEquals(postalCode, order.getPostalCode());     
	    assertEquals(2, order.getItems().size());  
	      
	    Optional<OrderItem> item1 = order.getItem(product1.getId());  
	    Optional<OrderItem> item2 = order.getItem(product2.getId());  
	      
	    assertTrue(item1.isPresent());  
	    assertEquals(product1.getPrice(), item1.get().getProductPrice());  
	    assertEquals(quantity1, item1.get().getQuantity());  
	    assertTrue(item2.isPresent());  
	    assertEquals(product2.getPrice(), item2.get().getProductPrice());  
	    assertEquals(quantity2, item2.get().getQuantity());  
	    assertTrue(user.getShoppingCart().isEmpty());  
	      
	}

...

}
```

# 2.Problemas de configuración
Hay parte de la configuración que no es adecuada para la ejecución de las pruebas automatizadas. 

```
spring:
  datasource:
    url: @dataSource.url@  //jdbc:mysql://.../pa?...
    username: @dataSource.user@  //pa
    password: @dataSource.password@  //pa

    dbcp2:  //más de una conexión en el pool
      max-total: 4 
      max-idle: 2

  jpa:
    hibernate:
      ddl-auto: none

```

## 2.1.Solución
Además de la configuración general, Spring permite tener configuración específica asociada a perfiles. Un perfil generalmente es un entorno de ejecución. Para tener una configuración asociada a un perfil con Spring Boot podemos crear el fichero `application-{perfil}.{propierties,yml}`. Se suelen redefinir propiedades de la configuración general.

Se puede especificar el perfil al ejecutar el backend.

```
java –jar backend.jar --spring.profiles.active=production
```

Podemos utilizar la notación `@ActiveProfiles` sobre las clases de pruebas de los servicios para especificar que perfiles se desea aplicar. Se define el fichero `src/test/resources/application-test.yml`.

```yml
spring:
  datasource:
    url: @dataSource.url@  //jdbc:mysql://.../patest?...
    username: @dataSource.user@  //pa
    password: @dataSource.password@  //pa

    dbcp2:  //una conexión en el pool
      max-total: 1
      max-idle: 1

  jpa:
    hibernate:
      ddl-auto: none
```

# 3. Equals y hashCode en entidades
No se pueden redefinir `equals` y `hashCode` en las entidades. Una posible estrategia es hacer cada caso de prueba en una transacción. Cada caso de prueba utiliza caché de primer nivel, por lo que nunca carga en memoria más de una instancia de una entidad con la misma clave primaria.

Por lo tanto, no es necesario redefinirlos.

# 4.Métodos de negocio en entidades
Algunos métodos se testean desde la capa de Servicios REST. No se prueban en la capa lógica de negocio porque no necesitan spring-test. Son los métodos de las clases OrderTest y ShoppingCartTest.