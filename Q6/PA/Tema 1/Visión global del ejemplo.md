[[Tema 1-Introducción al desarrollo con frameworks modernos]]
$\space$
## 1.PA Shop
PA Shop es un ejemplo de una aplicación web SPA en la que se basa la asignatura.
$\space$
### 1.1.Entidades
Una entidad es un objeto o concepto del mundo real que se puede distinguir claramente y del cual se puede recopilar información.

Se implementan con MySQL y se mapean mediante anotaciones de JPA (Java Persistence API). Cada entidad es una clase y se mapea a una tabla donde cada atributo o propiedad es una columna. Las relaciones se mapean de forma natural en lugar de utilizar claves foráneas. Por ejemplo, un pedido tendrá asociado un usuario, no el atributo `userID`.

![[entidades ejemplo pa.png]]
$\space$
### 1.2.DAOs
Un DAO (Data Access Object) es un patrón de diseño utilizado para proporcionar abstracción y encapsulamiento al acceso a fuentes de datos.

Al hacerlo con Spring disponemos de los métodos CRUD (Create, Read, Update, Delete) del `CrudRepository` implementados automáticamente. Además es capaz de implementar métodos de búsqueda mediante ciertas convenciones de nombrado. Por ejemplo:

```java
public interface OrderDao extends CrudRepository <Order, Long> {
	Slice<Order> findByUserIdOrderByDateDesc(Long userId, Pageable pageable);
}
```
$\space$
### 1.3.Lógica de negocio
Seguiremos un enfoque declarativo, es decir, describe el resultado deseado y es el sistema el encargado de determinar la mejor forma de hacerlo.

Cada método realizará una transacción gracias a la anotación a nivel de clase `@Transactional`. Si la ejecución no lanza excepciones o lanza una excepción checked se realiza un commit. Si lanza una `RuntimeException` o `Error` se realiza un rollback.

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
$\space$
### 1.4.Servicios
Utilizaremos servicios web REST. La anotación `@GetMapping` devolverá directamente el JSON con los atributos del DTO correspondiente.

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
$\space$
### 1.5.Acceso a servicios
Se hace una función de JavaScript para cada caso de uso que ofrece la capa servicios. Por ejemplo:

```javascript
export const findOrder = (orderId, onSuccess) => appFetch(`/shopping/orders/${orderId}`, config('GET', null), onSuccess);
```

Esta función se invoca desde la UI.

```javascript
backend.shoppingService.findOrder(orderId, order => {
	//procesar_orden
});
```
$\space$
### 1.6.UI
La UI se implementa con React y algunas librerías adicionales, como Redux. Sigue un enfoque orientado a componentes. Esto quiere decir que se implementa la interfaz como un conjunto de componentes, que son pequeños fragmentos HTML, que respondan a eventos del usuario.
$\space$
#### 1.6.1.Ventajas
Las ventajas del enfoque orientado a componentes son:
+ [p] Se basa en divide y vencerás.
+ [p] Los componentes son reusables, ya sea en la propia aplicación o en otras.
$\space$
#### 1.6.2.Componentes
Cada elementos de la página es un componente.

![[pagina web Bellas.png]]

Por ejemplo, el componente Buy sería:

```javascript
const Buy = ({cart}) => cart.items.length > 0 && (
	<div>
		<BuyForm/>  // genera el html del formulario de compra
		<ShoppingItemList list={cart}/> // genera el html del carrito
	</div>
);
```

