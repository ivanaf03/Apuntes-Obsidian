[[Tema 1-Introducción al desarrollo con frameworks modernos]]

## 1.Entidades
Una entidad es un objeto o concepto del mundo real que se puede distinguir claramente y del cual se puede recopilar información.

![[entidades ejemplo pa.png]]

Mediante las anotaciones de la API de JPA cada entidad se mapea a una tabla y cada propiedad a una columna. Las relaciones se mapean de forma natural en lugar de usar claves foráneas. Por ejemplo, `Order` tiene un `User`, no un `userID`.

## 2.DAOs
Un Data Access Object es un patrón de diseño utilizado para abstraer y encapsular el acceso a una fuente de datos.

Spring implementa automáticamente los métodos CRUD (Create, Read, Update, Delete). También es capaz de implementar métodos de búsqueda mediante convenciones de nombrado, por ejemplo:

```java
public interface OrderDao extends CrudRepository <Order, Long> {
	Slice<Order> findByUserIdOrderByDateDesc(Long userId, Pageable pageable);
}
```

## 3.Lógica de negocio
Haremos que todos los métodos sean transaccionales gracias a la anotación `@Transactional` a nivel de clase. Todas las operaciones de los DAOs se ejecutan dentro de la misma transacción. Si la ejecución no lanza ninguna excepción o lanza una excepción checked se hace un `commit`. Si lanza una `RuntimeException` o un error se hace un `rollback`.

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

## 4.Servicios
Utilizaremos servicios web REST.

![[get servicios.png]]

```java
@RequestMapping("/shopping")
public class ShoppingController { 

...

	@GetMapping("/orders/{orderId}")
	public OrderDto findOrder(@RequestAttribute Long userId, @PathVariable Long orderId) throws InstanceNotFoundException, PermissionException {
	return toOrderDto(shoppingService.findOrder(userId, orderId));
	} 
}
```

La anotación `@GetMapping` devolverá directamente el JSON con los atributos del DTO correspondiente.

## 5.Acceso a servicios
Se realiza una función por cada caso de uso:

```javascript
export const findOrder = (orderId, onSuccess) => appFetch(`/shopping/orders/${orderId}`, config('GET', null), onSuccess);
```

Se invoca desde la UI como:

```javascript
backend.shoppingService.findOrder(orderId, order => {
	//procesar_orden
});
```

## 6.UI
La UI se implementa con React y algunas librerías adicionales. Se enfoca a componentes, es decir, el desarrollador implementa la UI como un conjunto de pequeños fragmentos HTML que responden a los eventos del usuario.

### 6.1.Ventajas
Las ventajas de este enfoque son:
+ [p] Se basa en divide y vencerás.
+ [p] Genera componentes reusables.

### 6.2.Componentes
Cada elemento de la página es un componente.

![[pagina web Bellas.png]]

```javascript
//componente
const Buy = ({cart}) => cart.items.length > 0 && (
	<div>
		<BuyForm/> //genera el html del formulario de compra
		<ShoppingItemList list={cart}/> //html del carrito
	</div>
);
```

