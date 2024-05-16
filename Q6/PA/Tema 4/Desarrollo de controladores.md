[[Tema 4-Capa de servicios REST con Spring]]
$\space$
## 1.Enfoque
Se define un controlador por cada servicio local. Reciben peticiones HTTP e invocan un método de un servicio local. Internamente spring-web utiliza la API `Servlet`.
$\space$
### 1.1.Ventajas
Las ventajas de este enfoque son:
+ Mayor nivel de abstracción.
+ Los controladores tienen la misma cantidad de métodos públicos que el servicio local.
+ Se pueden usar anotaciones para manejar peticiones HTTP.
+ La conversion de JSON a DTO es automática.
$\space$
## 2. Esquema

![[controladores.png]]
$\space$
### 2.1.UserController

| Recurso                      | Método | Entrada                                                 | Salida                      |
| ---------------------------- | ------ | ------------------------------------------------------- | --------------------------- |
| /users/signUp                | POST   | UserDto [body]                                          | AuthenticatedUserDto [body] |
| /users/login                 | POST   | LoginParamsDto [body]                                   | AuthenticatedUserDto [body] |
| /users/loginFromServiceToken | POST   | userId [jwt]                                            | AuthenticatedUserDto [body] |
| /users/{id}                  | PUT    | userId [jwt], id [path], UserDto [body]                 | UserDto [body]              |
| /users/{id}/changePassword   | POST   | userId [jwt], id [path], ChangePasswordParamsDto [body] |                             |

En las URL 1, 2 y 3 se usa overloading POST porque no corresponden a operaciones CRUD. El `AuthenticatedUserDto` incluye los datos del perfil del usuario, excepto la contraseña y el carrito para que sean cacheados por el frontend. El `userID` se pasa de forma segura mediante un JSON Web Token (JWT).
$\space$
### 2.2.CatalogController

| Recurso                | Método | Entrada                                            | Salida                              |
| ---------------------- | ------ | -------------------------------------------------- | ----------------------------------- |
| /catalog/categories    | GET    |                                                    | List\<CategoryDto>, [body]          |
| /catalog/products/{id} | GET    | id [path]                                          | ProductDto [body]                   |
| /catalog/products      | GET    | categoryId [param], keywords [param], page [param] | BlockDto\<ProductSummaryDto> [body] |
$\space$
### 2.3.ShoppingController

| Recurso                                                                 | Método | Entrada                                                                             | Salida                            |
| ----------------------------------------------------------------------- | ------ | ----------------------------------------------------------------------------------- | --------------------------------- |
| /shopping/shoppingcarts/{shoppingCartId}/addToShoppingCart              | POST   | userId [jwt], shoppingCartId [path], AddToShoppingCartParamsDto [body]              | ShoppingCartDto [body]            |
| /shopping/shoppingcarts/{shoppingCartId}/updateShoppingCartItemQuantity | POST   | userId [jwt], shoppingCartId [path], UpdateShoppingCartItemQuantityParamsDto [body] | ShoppingCartDto [body]            |
| /shopping/shoppingcarts/{shoppingCartId}/removeShoppingCartItem         | POST   | userId [jwt], shoppingCartId [path], RemoveShoppingCartItemParamsDto [body]         | ShoppingCartDto [body]            |
| /shopping/shoppingcarts/{shoppingCartId}/buy                            | POST   | userId [jwt], shoppingCartId [path], BuyParamsDto [body]                            | Long [body]                       |
| /shopping/orders/{orderId}                                              | GET    | userId [jwt], orderId [path]                                                        | OrderDto [body]                   |
| /shopping/orders                                                        | GET    | userId [jwt], page [param]                                                          | BlockDto\<OrderSummaryDto> [body] |

En las URL 1, 2, 3 y 4 se usa overloading POST porque no corresponden a operaciones CRUD. `ShoppingCartDTO` es la nueva representación del carrito, que será cacheada por el frontend. El `userID` se pasa de forma segura mediante un JSON Web Token (JWT).
$\space$
## 3.Ejemplos
Veamos algunos ejemplos de peticiones en PA Shop.
$\space$
### 3.1.Ejemplo 1


![[springwebjsontodto.png]]

![[rest 1.png]]

![[rest 1 2.png]]

```java
@RestController
@RequestMapping("/shopping")
public class ShoppingController { 

...

    @Autowired 
    private ShoppingService shoppingService; 

...
    
    @GetMapping("/orders/{orderId}") // el ID vale 12
    public OrderDto findOrder(@RequestAttribute Long userId, @PathVariable Long orderId) throws InstanceNotFoundException, PermissionException { 
        return toOrderDto(shoppingService.findOrder(userId, orderId));  // convierte el JSON a DTO
    } 
}
```

La anotación `@RestController` se usa en todos los controladores. Funciona de forma similar a `@Service`, crea un bean del controlador en el contenedor de Spring. Por tanto, se puede usar `@Autowired` para inyectarle el servicio local asociado.
$\space$
#### 3.1.1.Mapping de peticiones HTTP
Con la anotación `@RequestMapping` se indica que las peticiones dirigidas a un path que comience por ese valor son procesadas por el controlador correspondiente. 

Con `@{Get, Post, Put, Delete}Mapping` se especifica en el método que tipo de petición HTTP es. El path indicado mapea la petición con el método correspondiente. Se puede capturar una parte del path entre llaves como sucede con `orderId`. Se inyectará en un parámetro del método, nombrado igual, con `@PathVariable`. 
$\space$
#### 3.1.2.Conversión de JSON a DTO
Para convertir de JSON a DTO o viceversa se usa Jackson. Los nombres de los campos del JSON tiene que ser iguales a los getter y setter de los DTOs. Soporta muchos tipos de Java. 

La fecha se puede modelar tanto como `LocalDateTime` como con un `long`. El frontend se encarga de convertirla a un Date de JS.

```java
public class OrderConversor {  
    private OrderConversor() {}  
    
    public final static List<OrderSummaryDto> toOrderSummaryDtos(List<Order> orders) {  
        return orders.stream()
                     .map(o -> toOrderSummaryDto(o))
                     .collect(Collectors.toList());  
    }    
    
    public final static OrderDto toOrderDto(Order order) {  
        List<OrderItemDto> items = order.getItems().stream()
                                                    .map(i -> toOrderItemDto(i))
                                                    .collect(Collectors.toList());  
        items.sort(Comparator.comparing(OrderItemDto::getProductName));  
        
        return new OrderDto(order.getId(), 
                            items, 
                            toMillis(order.getDate()), 
                            order.getTotalPrice(),  // patrón Domain Model
                            order.getPostalAddress(), 
                            order.getPostalCode());  
    }  
    
    private final static OrderItemDto toOrderItemDto(OrderItem item) {  
        return new OrderItemDto(item.getId(), 
                                item.getProduct().getId(), 
                                item.getProduct().getName(), 
                                item.getProductPrice(),  
                                item.getQuantity());  
    }  
}
```
$\space$
### 3.1.Ejemplo 2

![[ejemplo2controller.png]]

```java
@GetMapping("/products")
public BlockDto<ProductSummaryDto> findProducts(
    @RequestParam(required=false) Long categoryId,
    @RequestParam(required=false) String keywords, // keywords = 200
    @RequestParam(defaultValue="0") int page) {
    
    Block<Product> productBlock = catalogService.findProducts(categoryId, keywords != null ? keywords.trim() : null, page, 10);
    
    return new BlockDto<>(toProductSummaryDtos(productBlock.getItems()), productBlock.getExistMoreItems());
}
```

La anotación `@RequestParam` permite inyectar un atributo de un parámetro HTTP en el método de forma similar a `@PathVariable`. Con `required=false` evita que sea obligatorio el parámetro en la petición para el mapeo. Si no se envía se pone a nulo o toma el valor indicado con `defaultValue`.
$\space$
### 3.1.Ejemplo 3

![[ejemplo3controller.png]]

```java
@PostMapping("/shoppingcarts/{shoppingCartId}/buy")  // shoppingCartId = 12 
public Long buy(
    @RequestAttribute Long userId, 
    @PathVariable Long shoppingCartId,
    @Validated @RequestBody BuyParamsDto params)
    throws InstanceNotFoundException, PermissionException, EmptyShoppingCartException {
    
    return shoppingService.buy(userId, shoppingCartId, params.getPostalAddress(), params.getPostalCode()).getId();
}
```

La anotación `@RequestBody` hace lo mismo que `@RequestParam` pero con el cuerpo de la petición.