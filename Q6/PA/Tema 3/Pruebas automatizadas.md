[[Tema 3-Capa lógica de negocio con Spring]]
$\space$
## 1.Tests del servicio
Cada cada de prueba se ejecuta en un método anotado con `@Test`. Los casos de prueban son independientes entre sí. Se pueden crear DAOs en las clases de prueba cuando sea necesario.

En el ejemplo se usan dos bases de datos:
+ **pa:** para probar la aplicación como desarrollador.
+ **patest:** para ejecutar los test.
$\space$
### 1.1.Tests con Spring
La librería spring-test permite implementar fácilmente las clases de prueba de la capa lógica de negocio. Trabaja con JUnit5. Gracias a la anotación `@SpringBootTest` podemos:
+ Ejecutar las pruebas con JUnit5.
+ Utilizar las características de Spring Boot.
+ Inyectar beans en as clases de prueba.
$\space$
#### 1.1.1.Estrcutura
Los test tienen la siguiente forma:

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

Se pueden tener múltiples perfiles con Spring. Para ello basta con crear el fichero `application-(perfil).{yml, properties}` asociado. La anotación `@ActivateProfile` permite cargar el perfil test definido en los archivos de configuración. Este perfil utiliza la base de datos patest. Al ejecutar el backend se puede especificar el perfil que se considere.

```properties
# application-test.yml
spring:  
  datasource:  
    url: @testDataSource.url@  
    # jdbc:mysql://.../patest?...
    username: @testDataSource.user@  
    # pa
    password: @testDataSource.password@  
    # pa
    dbcp2:  
      max-total: 1  
      max-idle: 1

# pom.xml
<dataSource.baseUrl>jdbc:mysql://localhost/pa</dataSource.baseUrl>  
<dataSource.url>${dataSource.baseUrl}?useSSL=false&amp;allowPublicKeyRetrieval=true&amp;serverTimezone=Europe/Madrid</dataSource.url>  
<testDataSource.url>${dataSource.baseUrl}?testuseSSL=false&amp;allowPublicKeyRetrieval=true&amp;serverTimezone=Europe/Madrid</testDataSource.url>
```

Con `@Transactional` a nivel de clase se asegura que cada caso de prueba vaya en una transacción junto a los DAOs y servicios que invoque. Por defecto la librería termina todos los métodos con rollback. Esto deshace los cambios hechos en la base de datos durante la transacción sin tener que hacerlo de forma implícita.
$\space$
#### 1.1.2.Ejemplo: ShoppingServiceTest

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

...

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
$\space$
### 1.2.Estrategias de redefinición de equals y hashCode
Existen muchas estrategias para redefinir `equals` y `hashCode` en las entidades. La más sencilla de todas es que como cada prueba se ejecuta en una sola transacción y dentro de la transacción nunca se cargará más de una instancia de la misma entidad gracias a la caché de primer nivel, podemos usar la igualdad referencial. Nunca habrá dos instancias duplicadas en memoria, por tanto, no es necesario redefinir estos métodos.
$\space$
## 2.Métodos de negocio en entidades
Algunos métodos de negocio no se usan en el servicio, sino que se trabaja con ellos en la capa servicios REST. No quieren spring-test. Por ejemplo:

```java
public class OrderTest {  

    private Product createProduct(String name, BigDecimal price) {  
        return new Product(name, "description", price, new Category());  
    }    

    @Test  
    public void testGetTotalPrice() {  
        Product product1 = createProduct("product1", new BigDecimal("10.5"));       
        Product product2 = createProduct("product2",  new BigDecimal("15.3"));  

        Order order = new Order();  

        BigDecimal price1 = product1.getPrice().add(new BigDecimal(1));  
        int quantity1 = 1;  
        OrderItem item1 = new OrderItem(product1, price1, quantity1);  

        BigDecimal price2 = product2.getPrice().add(new BigDecimal(1));  
        int quantity2 = 2;  
        OrderItem item2 = new OrderItem(product2, price2, quantity2);  

        order.addItem(item1);  
        order.addItem(item2);  

        BigDecimal totalPrice = price1.multiply(new BigDecimal(quantity1))  
            .add(price2.multiply(new BigDecimal(quantity2)));  

        assertEquals(totalPrice, order.getTotalPrice()); // prueba de getTotalPrice
    }  
}
```