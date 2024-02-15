[[Tema 2-Capa acceso a datos con Spring y JPA]]

## DAOs
Spring Data permite desarrollar DAOs para diferentes fuentes de datos. Las interfaces no revelan ningún detalle de implementación. 

### Operaciones CRUD
```java
package es.udc.pashop.backend.model.entities;

import org.springframework.data.repository.CrudRepository;

public interface OrderItemDao extends CrudRepository<OrderItem, Long> {
}
```

Todos los DAO extienden de `CrudRepository`. Por ejemplo:
```java
//buscar por id
Long id = ...;
Optional<OrderItem> item = orderItemDao.findById(id);
if (!item.isPresent()) {
    throw new ItemNotFoundException("No se encontró el elemento de pedido con el ID: " + id);
}
process(item.get());

//añadir
OrderItem item = new OrderItem(...);
orderItemDao.save(item);

//eliminar
Long id = ...;
Optional<OrderItem> item = orderItemDao.findById(id);
if (!item.isPresent()) {
    throw new ItemNotFoundException("No se encontró el elemento de pedido con el ID: " + id);
}
orderItemDao.delete(item.get());
```

### Operaciones de búsqueda
Se pueden definir métodos de búsqueda con convenciones de nombrado. Se usan los prefijos `findBy` y `existsBy`. Por ejemplo:
```java
public interface UserDao extends CrudRepository<User, Long> {
    boolean existsByUserName(String userName);
    Optional<User> findByUserName(String userName);
}
```

Busca por el primer parámetro que recibe.

Otros ejemplos serían:
```java
List<User> findByFirstNameAndLastName(String firstName, String lastName);

List<User> findByFirstNameOrLastName(String firstName, String lastName);

List<User> findByFirstNameOrderByLastNameAsc( String firstName);

List<User> findByFirstNameOrderByLastNameDesc( String firstName);
```

### Paginación
```java
public interface OrderDao extends CrudRepository<Order, Long> { 
	List findByUserIdOrderByDateDesc(Long userId);
 }
```

En este ejemplo Order no tiene un userId. Pero si tiene un user, que tiene a su vez un userId. Por tanto coge el valor `order.getUser().getUserId()`.

Un usuario puede hacer muchísimos pedidos. Esto limita la escalabilidad (demasiadas peticiones concurrentes) y la usabilidad (UI con todos los datos de todos los pedidos a la vez).

Para solucionar esto se realiza una paginación. 
```java
import org.springframework.data.domain.Pageable;
import org.springframework.data.domain.Slice;
import org.springframework.data.repository.CrudRepository;

public interface OrderDao extends CrudRepository<Order, Long> {
    Slice<Order> findByUserIdOrderByDateDesc(Long userId, Pageable pageable);
}
```

Los métodos de búsqueda reciben un parámetro Pageable que especifica el rango de resultados que puede sacar de la base de datos. Además devuelven los datos con un valor de tipo Slice que indica si todavía hay más datos.
```java
import org.springframework.data.domain.PageRequest;

int page = ...; // Número de página actual
int size = ...; // Tamaño de la página
Slice<Order> slice = orderDao.findByUserIdOrderByDateDesc(userId, PageRequest.of(page, size));
List<Order> orders = slice.getContent(); 
boolean existMoreOrders = slice.hasNext(); 
```

![[paginación.png]]
Es importante que la paginación siga algún tipo de orden. La implementación por debajo utiliza la API de JDBC.

# JPQL
Cuando las convenciones de nombrado no son viables podemos usar JPQL. Es un lenguaje declarativo que perite lanzar consultas en JPA. También se puede hacer mediante el API Criteria.

## Sintaxis
Es parecido a SQL. No utiliza nombre de tablas y columnas, sino entidades y propiedades.
```sql
select u from User where u.userName=:userName
```

`:userName` es un parámetro nombrado. Funciona similar a `?` en SQL. Permite sustituirlo por un valor antes de lanzar la consulta. 

+ [>] **Al lanzar una consulta:**
+ Busca el nombre de la tabla y de las columnas a las que referencian los atributos.
+ Traduce JPQL a SQL.
+ Ejecuta la consulta mediante JDBC.
+ Recupera las filas y las devuelve como entidades.

### Otros ejemplos
```sql
select u from User where u.firstName=:firstName and u.lastName=:lastName

select u from User u where u.firstName=:firstname or u.lastName=:lastName

select u from User u where u.firstName=:firstName order by u.lastName asc

select u from User u where u.firstName=:firstName order by u.lastName desc

select o from Order o where o.user.id=:userId order by o.date desc
```

## Querys
Spring Data JPA permite lanzar consultas de forma muy simple utilizando `@Query`. Se utiliza `?i` en lugar de parámetros nombrados.
```Java
@Query("select u from User u where u.userName=?1")
Optional<User> findUser(String userName);

@Query("select u from User u where u.firstName=?1 or u.lastName=?2")
List<User> findUsers(String firstName, String lastName);
```

Esta notación no es válida en consultas dinámicas. Por ejemplo, la búsqueda por palabras clave.

+ [>] **Hacemos:**
+ Definimos estas operaciones en una interfaz adicional `CustomizedProductDao`.
+ La implementamos en `CustomizedProductDaoImpl` utilizando la API de JPA para lanzar la consulta.
+ `ProductDao` extiende `CustomizedProductDao`.




