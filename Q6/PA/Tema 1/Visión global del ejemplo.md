[[Tema 1-Introducción al desarrollo con frameworks modernos]]

## Entidades
![[entidades ejemplo pa.png]]Cada entidad se mapea a una tabla y cada propiedad a una columna. Las relaciones se mapean de forma natural (Order tiene un User, no un userID).

## DAOs
```java
public interface OrderDao extends CrudRepository {
	Slice findByUserIdOrderByDateDesc(Long userId, Pageable pageable);
}
```

Spring implementa automáticamente los métodos CRUD. También es capaz de implementar métodos de búsqueda mediante convenciones de nombrado.

## Lógica de negocio
`@Transactional` permite que todos los métodos sean transaccionales. Todas las operaciones de los DAOs se ejecutan dentro de la misma transacción. Si la ejecución no lanza ninguna excepción se hace un commit. Si se lanza una excepción checked también. Si lanza una excepción de runtime o un error se hace un rollback.

```java
@Transactional
public class ShoppingServiceImpl implements ShoppingService {

    @Override
    public Order buy(Long userId, Long shoppingCartId, String postalAddress, String postalCode)
            throws InstanceNotFoundException, PermissionException, EmptyShoppingCartException {

        ShoppingCart shoppingCart = permissionChecker
                .checkShoppingCartExistsAndBelongsTo(shoppingCartId, userId);

        if (shoppingCart.isEmpty()) {
            throw new EmptyShoppingCartException();
        }

        Order order = new Order(shoppingCart.getUser(), LocalDateTime.now(), postalAddress, postalCode);
        orderDao.save(order);

        for (ShoppingCartItem shoppingCartItem : shoppingCart.getItems()) {
            OrderItem orderItem = new OrderItem(
                    shoppingCartItem.getProduct(),
                    shoppingCartItem.getProduct().getPrice(),
                    shoppingCartItem.getQuantity());
            order.addItem(orderItem);
            orderItemDao.save(orderItem);
            shoppingCartItemDao.delete(shoppingCartItem);
        }

        shoppingCart.removeAll();

        return order;
    }
}
```

## Servicios
![[get servicios.png]]
