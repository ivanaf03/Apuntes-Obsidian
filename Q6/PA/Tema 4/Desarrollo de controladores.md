[[Tema 4-Capa de servicios REST con Spring]]

# 1.Enfoque
Se define una clase controlador por cada servicio local. Funcionan de forma similar a los `Servlets`. Reciben peticiones HTTP y delegan en el método del servicio local correspondiente.

Las ventajas de que trabajen a un nivel de abstracción mucho mayor son:
+ [p] Tienen los mismos métodos públicos que el servicio local asociado.
+ [p] Se usan anotaciones para manejar peticiones HTTP.
+ [p] La conversión de JSON a DTO es automática.

# 2. Esquema

![[controladores.png]]

## 2.1.UserController
| Recurso                      | Método | Entrada                                                 | Salida                      |
| ---------------------------- | ------ | ------------------------------------------------------- | --------------------------- |
| /users/signUp                | POST   | UserDto [body]                                          | AuthenticatedUserDto [body] |
| /users/login                 | POST   | LoginParamsDto [body]                                   | AuthenticatedUserDto [body] |
| /users/loginFromServiceToken | POST   | userId [jwt]                                            | AuthenticatedUserDto [body] |
| /users/{id}                  | PUT    | userId [jwt], id [path], UserDto [body]                 | UserDto [body]              |
| /users/{id}/changePassword   | POST   | userId [jwt], id [path], ChangePasswordParamsDto [body] |                             |

## 2.2.Catalog controller
| Recurso                | Método | Entrada                                            | Salida                              |
| ---------------------- | ------ | -------------------------------------------------- | ----------------------------------- |
| /catalog/categories    | GET    |                                                    | List\<CategoryDto>, [body]          |
| /catalog/products/{id} | GET    | id [path]                                          | ProductDto [body]                   |
| /catalog/products      | GET    | categoryId [param], keywords [param], page [param] | BlockDto\<ProductSummaryDto> [body] |

## 2.3.ShoppingController
| Recurso                                                                 | Método | Entrada                                                                             | Salida                            |
| ----------------------------------------------------------------------- | ------ | ----------------------------------------------------------------------------------- | --------------------------------- |
| /shopping/shoppingcarts/{shoppingCartId}/addToShoppingCart              | POST   | userId [jwt], shoppingCartId [path], AddToShoppingCartParamsDto [body]              | ShoppingCartDto [body]            |
| /shopping/shoppingcarts/{shoppingCartId}/updateShoppingCartItemQuantity | POST   | userId [jwt], shoppingCartId [path], UpdateShoppingCartItemQuantityParamsDto [body] | ShoppingCartDto [body]            |
| /shopping/shoppingcarts/{shoppingCartId}/removeShoppingCartItem         | POST   | userId [jwt], shoppingCartId [path], RemoveShoppingCartItemParamsDto [body]         | ShoppingCartDto [body]            |
| /shopping/shoppingcarts/{shoppingCartId}/buy                            | POST   | userId [jwt], shoppingCartId [path], BuyParamsDto [body]                            | Long [body]                       |
| /shopping/orders/{orderId}                                              | GET    | userId [jwt], orderId [path]                                                        | OrderDto [body]                   |
| /shopping/orders                                                        | GET    | userId [jwt], page [param]                                                          | BlockDto\<OrderSummaryDto> [body] |

# 3.Ejemplos
## 3.1.Ejemplo 1

![[rest 1.png]]

![[rest 1 2.png]]

```java
@GetMapping("/orders/{orderId}")  
public OrderDto findOrder(@RequestAttribute Long userId, @PathVariable Long orderId)   
    throws InstanceNotFoundException, PermissionException {  
      
    return toOrderDto(shoppingService.findOrder(userId, orderId));  
      
}
```