[[Tema 3-Capa lógica de negocio con Spring]]
$\space$
## 1.Transaccionalidad con enfoque declarativo
Spring permite usar un enfoque declarativo para implementar la transaccionalidad de los métodos de los servicios locales. Esto quiere decir que en lugar de escribir manualmente el código para gestionar las transacciones, se puede hacer con anotaciones o ficheros de configuración.
$\space$
### 1.1.Anotación @Transactional
La anotación `@Transactional` permite especificar la transaccionalidad. Puede usarse:
+ **A nivel de clase:** se aplica a todos los métodos públicos.
+ **A nivel de método:** sobrescribe la transaccionalidad indicada a nivel de clase.
$\space$
#### 1.1.1.Uso de la anotación
Al invocar a un método anotado con `@Transactional` dentro de una transacción, el método se une a ella. Si se hace desde fuera se crea una nueva transacción.

Las operaciones de los DAOs y servicios se unen a la transacción. Cuando esta termina puede lanzar:
+ **Commit:** si ha terminado bien o ha lanzado una excepción checked.
+ **Rollback:** si ha terminado con un `Error` o con una `RuntimeException`.
$\space$
#### 1.1.2.Operaciones de lectura
En operaciones de lectura se puede especificar `readOnly = true` para realizar optimizaciones.

```java
@Override  
@Transactional(readOnly=true)  
public Event findEventById(Long id) throws InstanceNotFoundException {  
    Optional<Event> event = eventDao.findById(id);  
    if (event.isEmpty()) {  
        throw new InstanceNotFoundException("project.entities.event", id);  
    }    return event.get();  
}
```
$\space$
### 1.2.Ejemplos de transaccionalidad

```java
@Service
@Transactional
public class ShoppingServiceImpl implements ShoppingService {
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
            OrderItem orderItem = new OrderItem(
                shoppingCartItem.getProduct(),
                shoppingCartItem.getProduct().getPrice(),
                shoppingCartItem.getQuantity()
            );
            order.addItem(orderItem);
            orderItemDao.save(orderItem);
            shoppingCartItemDao.delete(shoppingCartItem);
        }
        
        shoppingCart.removeAll();
        
        return order;
    }
}
```

Cuando la capa de servicios REST invoque a buy se inicia una transacción, ya que aparece `@Transactional` a nivel de clase. Al hacer ` ShoppingCart shoppingCart = permissionChecker.checkShoppingCartExistsAndBelongsTo(shoppingCartId, userId);` esta transacción se une a la actual. También se unen las operaciones de los DAOs. Todo se ejecuta en una sola transacción.
$\space$
## 2.Sistema de caché
El sistema de caché de JPA almacena en memoria objetos recuperados de la base de datos durante la ejecución de consultas. Esto significa que, si una entidad ha sido recuperada previamente de la base de datos y está almacenada en el caché, las consultas posteriores que soliciten la misma entidad no necesitarán acceder a la base de datos nuevamente. En su lugar, la entidad será recuperada directamente desde el caché, lo que puede mejorar significativamente el rendimiento de la aplicación al reducir la cantidad de consultas a la base de datos.
$\space$
### 2.1.Entidades en estado dirty
Si dentro de una transacción se modifica una entidad en memoria se dice que está en estado dirty hasta que se actualiza en BBDD. Sin embargo, si se hace desde dentro de una transacción Hibernate se encarga de actualizar la base de datos antes de terminal la transacción. No es necesario llamar al método save del DAO.

Por ejemplo, en `updateProfile`:

```java
@Override
public User updateProfile(Long id, String firstName, String lastName, String email) throws InstanceNotFoundException {
    // Recuperación del usuario
    User user = permissionChecker.checkUser(id);
    
    // Actualización del perfil del usuario
    user.setFirstName(firstName);
    user.setLastName(lastName);
    user.setEmail(email);
    
    // La transacción se completará automáticamente al finalizar el método
    // Hibernate detectará que la entidad está en estado "dirty" y lanzará una sentencia de actualización en BD antes de finalizar la transacción
    
    return user;
}
```
$\space$
### 2.2.Caché de primer nivel
La caché de primer nivel o caché de entidad, es una caché interna que mantiene Hibernate para almacenar en memoria las entidades recuperadas durante una transacción. Esta caché se asocia directamente con una instancia de la sesión de Hibernate y se limpia al finalizar la sesión o cuando se elimina explícitamente.

No se comparte entre transacciones.
$\space$
#### 2.2.1.Ejemplos

```java
// Ejemplo 1: Guardar una nueva categoría en la base de datos y luego recuperarla
public void example1() {
    // Crear una nueva categoría
    Category category = new Category(...);
    
    // Guardar la categoría en la base de datos (INSERT)
    categoryDao.save(category); // Acceso a la base de datos (INSERT)
    
    // Recuperar la misma categoría de la base de datos
    // Como la entidad se guardó previamente en esta sesión de Hibernate, se recupera de la caché de primer nivel
    category = categoryDao.findById(category.getId()).get(); // No provoca acceso a la base de datos (está en caché)
}
```

```java
// Ejemplo 2: Recuperar un producto y luego obtener su categoría
public void example2(Long productId) {
    // Recuperar el producto de la base de datos
    Product product = productDao.findById(productId).get(); // Acceso a la base de datos (SELECT)
    
    // Obtener la categoría del producto
    Category category = product.getCategory(); // Proxy inicializado al obtener la categoría del producto
    
    // Acceder a la ID y el nombre de la categoría
    Long categoryId = category.getId(); // Acceso a la base de datos (inicialización del proxy)
    String categoryName = category.getName(); // No provoca acceso a la base de datos (el proxy ya está inicializado)
    
    // Recuperar la misma categoría de la base de datos
    // Como la entidad se recuperó previamente en esta sesión de Hibernate, se recupera de la caché de primer nivel
    category = categoryDao.findById(categoryId).get(); // No provoca acceso a la base de datos (está en caché)
}
```
$\space$
#### 2.2.2.Cache de nivel 2
JPA también dispone de caché de nivel 2. Permite cachear entidades y resultados de consultas a nivel de servicio. Se puede activar en la configuración. Es la memoria que JPA pone a disposición de la aplicación para guardar objetos de uso frecuente y conseguir una mejora en el rendimiento.