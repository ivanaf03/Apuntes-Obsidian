[[Tema 2-Capa acceso a datos con Spring y JPA]]
$\space$
## 1.Operaciones de Spring Data
Spring Data permite desarrollar DAOs para diferentes fuentes de datos. Las interfaces no revelan ningún detalle de implementación. En la mayoría de casos Spring Data implementa los DAO en tiempo de ejecución.
$\space$
### 1.1.Operaciones CRUD
Todos los DAO extienden de `CrudRepository`. Define varias operaciones Create, Read, Update y Delete. Sin embargo algunos DAO pueden necesitar extender de otras interfaces.

```java
package es.udc.pashop.backend.model.entities;

import org.springframework.data.repository.CrudRepository;

public interface OrderItemDao extends CrudRepository<OrderItem, Long> {
}
```
$\space$
#### 1.1.1.Ejemplos de operaciones CRUD

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
$\space$
### 1.2.Operaciones de búsqueda
Se pueden definir métodos de búsqueda con convenciones de nombrado. Se usan los prefijos `findBy` y `existsBy`. Buscan por el primer parámetro que reciben en notación CamelCase. Al usar `findBy` se puede devolver un `Optional` si se sabe que puede devolver ninguna o una instancia como mucho.

```java
public interface UserDao extends CrudRepository<User, Long> {
    boolean existsByUserName(String userName);
    Optional<User> findByUserName(String userName);
}
```
$\space$
#### 1.2.1.Otros ejemplos de búsquedas

```java
List<User> findByFirstNameAndLastName(String firstName, String lastName);

List<User> findByFirstNameOrLastName(String firstName, String lastName);

List<User> findByFirstNameOrderByLastNameAsc(String firstName);

List<User> findByFirstNameOrderByLastNameDesc(String firstName);

List <Order>findByUserIdOrderByDateDesc(Long userId);
```
$\space$
#### 1.2.2.Paginación de búsquedas
Un usuario puede hacer muchísimos pedidos. Esto limita la escalabilidad, ya que puede haber demasiadas peticiones concurrentes, y la usabilidad, la UI tendría todos los datos de todos los pedidos a la vez. Para solucionar esto se realiza una paginación.

```java
import org.springframework.data.domain.Pageable;
import org.springframework.data.domain.Slice;
import org.springframework.data.repository.CrudRepository;

public interface OrderDao extends CrudRepository<Order, Long> {
    Slice<Order> findByUserIdOrderByDateDesc(Long userId, Pageable pageable);
}
```

Los métodos de búsqueda reciben un parámetro `Pageable`, que especifica el rango de resultados que puede sacar de la base de datos. Además devuelven los datos con un valor de tipo `Slice` que indica si todavía hay más datos.

```java
import org.springframework.data.domain.PageRequest;

int page = ...; // Número de página actual
int size = ...; // Tamaño de la página

Slice<Order> slice = orderDao.findByUserIdOrderByDateDesc(userId, PageRequest.of(page, size));

List<Order> orders = slice.getContent(); 
boolean existMoreOrders = slice.hasNext(); 
```

En frontend se vería así:

![[paginación.png]]

Es importante que la paginación siga algún tipo de orden. La implementación por debajo utiliza la API de JDBC para informar a la BBDD que solo devuelva las filas que se encuentran entre page\*size y page\*size+size-1.
$\space$
## 2. JPQL
Cuando las convenciones de nombrado no son viables podemos usar JPQL. Es un lenguaje declarativo que permite lanzar consultas en JPA. También se puede hacer mediante la API Criteria.
$\space$$\space$
### 2.1. Sintaxis
Es parecido a SQL. No utiliza nombre de tablas y columnas, sino entidades y atributos.

```sql
select u from User u where u.userName=:userName

-- :userName es un parámetro nombrado. Funciona similar a `?` en SQL. JPA permite sustituirlo por un valor antes de lanzar la consulta. 
```

Al lanzar una consulta JPQL:
1. Busca el nombre de la tabla y de las columnas a las que referencian los atributos.
2. Traduce JPQL a SQL.
3. Ejecuta la consulta mediante JDBC.
4.  Recupera las filas y las devuelve como instancias de entidades.
$\space$$\space$
#### 2.1.2.Otros ejemplos

```sql
select u from User where u.firstName=:firstName and u.lastName=:lastName

select u from User u where u.firstName=:firstname or u.lastName=:lastName

select u from User u where u.firstName=:firstName order by u.lastName asc

select u from User u where u.firstName=:firstName order by u.lastName desc

select o from Order o where o.user.id=:userId order by o.date desc
```
$\space$$\space$
### 2.2. Querys
Spring Data JPA permite lanzar consultas de forma muy simple utilizando `@Query`. Se utiliza `?i` en lugar de parámetros nombrados, siendo `i` el parámetro número i el método. Empieza a contar en 1, no en 0.

```Java
@Query("select u from User u where u.userName=?1")
Optional<User> findUser(String userName);

@Query("select u from User u where u.firstName=?1 or u.lastName=?2")
List<User> findUsers(String firstName, String lastName);

@Query("SELECT o FROM Order o WHERE o.user.id = ?1 ORDER BY o.date DESC") Slice findOrders(Long userId, Pageable pageable); // Con paginación
```

Esta notación no es válida en consultas dinámicas. Por ejemplo, una búsqueda por palabras clave. En estos casos es necesario:
1. Definir estas operaciones en una interfaz adicional, por ejemplo, `CustomizedProductDao`.
2. Implementar la consulta en `CustomizedProductDaoImpl` utilizando la API de JPA para lanzar la consulta.
3. `ProductDao` extiende `CustomizedProductDao`.




