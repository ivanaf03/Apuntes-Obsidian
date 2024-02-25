[[Tema 3-Capa lógica de negocio con Spring]]

# 1.Transaccionalidad declarativa
Spring permite usar un enfoque declarativo para implementar la transaccionalidad de los métodos de los servicios locales. Consiste en gestionar transacciones de manera fácil y transparente mediante la declaración de comportamiento transaccional en el nivel de código fuente, en lugar de escribir código manualmente para iniciar, confirmar o revertir transacciones. Se puede especificar mediante:
+ [>] Ficheros de configuración.
+ [>] La anotación `@Transactional`.

## 1.1.Anotación @Transactional
Se puede declarar:
+ [>] *A nivel de clase:* se aplica a todos los métodos públicos.
+ [>] *A nivel de método:* sobrescribe la semántica especificada a nivel de clase.

$\space$
Al invocar a un método anotado puede estar:
+ *Dentro de una transacción:* se hace en ella.
+ *Fuera de una transacción:* se crea una nueva.

$\space$
Las operaciones que se invoquen en los DAOs y servicios se unen a la transacción. Esta terminará con commit o rollback, dependiendo si ha terminado bien o ha lanzado una excepción checked o si ha terminado con un error o con una `RuntimeException`.

Se puede concretar `@Transaction(readOnly=true)` si el método solo realiza lecturas para una mayor optimización.

## 1.2.Ejemplos
```java
@Override  
public Order buy(Long userId, Long shoppingCartId, String postalAddress, String postalCode)  
       throws InstanceNotFoundException, PermissionException, EmptyShoppingCartException {  
      
    ShoppingCart shoppingCart = permissionChecker.checkShoppingCartExistsAndBelongsTo(shoppingCartId, userId);  
      
    if (shoppingCart.isEmpty()) {  
       throw new EmptyShoppingCartException();  
    }  
      
    Order order = new Order(shoppingCart.getUser(), LocalDateTime.now(), postalAddress, postalCode);  
      
    orderDao.save(order);  
      
    for (ShoppingCartItem shoppingCartItem : shoppingCart.getItems()) {  
         
       OrderItem orderItem = new OrderItem(shoppingCartItem.getProduct(),  
          shoppingCartItem.getProduct().getPrice(), shoppingCartItem.getQuantity());  
         
       order.addItem(orderItem);  
       orderItemDao.save(orderItem);  
       shoppingCartItemDao.delete(shoppingCartItem);  
         
    }  
      
    shoppingCart.removeAll();  
  
    return order;  
  
}
```

Cuando se invoca desde la capa de servicios REST a buy se crea una transacción por la anotación a nivel de clase en ShoppingServiceImpl. Cuando se llama a `checkShoppingCartExistsAndBelongsTo` se une su transacción a la creada antes. Todo el método del ejemplo ocurrirá en una sola transacción.

```java
@Override  
@Transactional(readOnly=true)  
public Order findOrder(Long userId, Long orderId) throws InstanceNotFoundException, PermissionException {  
    return permissionChecker.checkOrderExistsAndBelongsTo(orderId, userId);  
}
```

# 2.Sistema de caché
## 2.1.Entidades en estado dirty
Una entidad está en estado dirty antes de acabar una transacción si se modifica una entidad en memoria. Al terminar Hibernate lanza la sentencia de actualización en base de datos.

## 2.2.Caché de primer nivel
Las implementaciones de JPA utilizan caché de primer nivel. Al ejecutar una transacción, el mapeador objeto-relacional cachea las instancias de las entidades que usa en esa transacción. Al terminarla se borra la caché. No se comparte entre transacciones.

![[cache de primer nivel.png]]

JPA también cuenta con transacciones de segundo nivel. Permite cachear entidades y resultados de consultas a nivel de servicio.