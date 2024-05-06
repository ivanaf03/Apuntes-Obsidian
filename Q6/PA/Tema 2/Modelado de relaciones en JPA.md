[[Tema 2-Capa acceso a datos con Spring y JPA]]
$\space$
## 1.Modelado de relaciones
Se pueden modelar relaciones 1:1, 1:N o M:N. Pueden ser unidireccionales o bidireccionales según el sentido de la navegación. Si solo podemos navegar de una clase a otra, es unidireccional. Si podemos navegar entre ambas es bidireccional.

Un truco que se suele usar con las relaciones M:N es utilizar relaciones 1:N con una entidad intermedia. No se considera buena práctica tener relaciones M:N.

Las entidades en una relación actúan como:
+ **Propietario:** entidad que contiene la clave foránea.
+ **Inverso:** en las relaciones bidireccionales, es el otro lado. En las relaciones unidireccionales no se habla de lado inverso.
$\space$
### 1.1.Relaciones 1:N
Se anotan los getters que permiten navegar de una entidad a otra con `@ManyToOne`, en el atributo con cardinalidad N y `@OneToMany`, en el atributo con cardinalidad 1. Se suele usar `Set` en este último atributo para devolver una colección de entidades.

En relaciones bidireccionales se utiliza `mappedBy` en el lado inverso. Especifica el atributo del otro lado de la relación (nombre del método getter sin get y la primera letra en minúscula, por ejemplo, getItem --> item).

La anotación `@JoinColumn` se coloca sobre el getter de la entidad propietaria de la relación. En una relación 1:N el lado propietario siempre es el lado N y en las 1:1 el lado 1, ya que el otro es siempre 0..1 para que el concepto de relación tenga sentido. Especifica el nombre de la columna que actúa como clave foránea.

En la anotación `@ManyToOne` la anotación `optional=false` indica que ese método nunca puede devolver nulos, por ejemplo, cada línea está asociada a un pedido obligatoriamente. En caso de `optional=true` indicaría una  cardinalidad de 0..1. `@OneToMany` no tiene el parámetro `optional`. No tendría sentido, ya que es normal que a veces no existen elementos del lado N. No se devolvería nulo, sino un conjunto vacío.
$\space$$\space$
#### 1.1.1.Ejemplo de relación entre Order y OrderItem

![[1N PA.png]]

```java
@Entity
@Table(name="OrderTable")
public class Order {
    ...

    private Set<OrderItem> items = new HashSet<>();

    @OneToMany(mappedBy="order")
    public Set<OrderItem> getItems() {
        return items;
    }

    public void setItems(Set<OrderItem> items) {
        this.items = items;
    }

    ...
}
```

```java
@Entity
public class OrderItem {
    ...

    private Order order;

    @ManyToOne(optional=false, fetch=FetchType.LAZY)
    @JoinColumn(name="orderId")
    public Order getOrder() {
        return order;
    }

    public void setOrder(Order order) {
        this.order = order;
    }

    ...
}
```
$\space$$\space$
### 1.2.Relaciones 1:1
Es idéntico a las relaciones 1:N, pero usando `@OneToOne` en ambos lados. Permite también especificar `optional`.
$\space$$\space$
#### 1.2.1.Ejemplo de relación entre User y ShoppingCart

![[11 PA.png]]

```java
@Entity
public class User {
    // Otros atributos y métodos de la clase

    private ShoppingCart shoppingCart;

    @OneToOne(mappedBy="user", optional=false, fetch=FetchType.LAZY)
    public ShoppingCart getShoppingCart() {
        return shoppingCart;
    }

    public void setShoppingCart(ShoppingCart shoppingCart) {
        this.shoppingCart = shoppingCart;
    }

    // Otros atributos y métodos de la clase
}
```

```java
@Entity
public class ShoppingCart {
    // Otros atributos y métodos de la clase

    private User user;

    @OneToOne(optional=false, fetch=FetchType.LAZY)
    @JoinColumn(name= "userId")
    public User getUser() {
        return user;
    }

    public void setUser(User user) {
        this.user = user;
    }

    // Otros atributos y métodos de la clase
}
```
$\space$$\space$
### 1.3.Relaciones unidireccionales
Cuando se modela una relación como unidireccional solo se anota el get del lado propietario, ya que no tienen lado inverso. No tendría sentido hacer, por ejemplo, `category.getProducts()`, ya que podría devolver muchísimos productos de golpe.
$\space$$\space$
#### 1.3.1.Ejemplo de relación entre Category y Product

![[relaciones unidireccionales.png]]
$\space$$\space$
## 2.Políticas de recuperación
Cuando queremos recuperar datos a veces sería necesario acceder a demasiadas cosas innecesarias. Por ejemplo, se queremos recuperar una instancia de BD de OrderItem hacemos:

```java
OrderItem item=entityManager.find(OrderItem.class, itemId)
```

Esto haría lo siguiente por defecto:
1. Recupera la instancia de OrderItem mediante un `select`.
2. Recupera el producto y el pedido asociados.
3. Recupera la categoría asociada al producto.
4. Recupera el ítem y el usuario asociados al pedido.
5. Para cada ítem del pedido y el usuario recuperaría todos los campos y así en bucle.
$\space$$\space$
### 2.1.Política eager
El problema anterior surge porque sigue una política eager. Para cada datos objeto se recuperan todos los datos.

JPA sigue esta política si una entidad tiene una relación `@xxxToOne` con otra. Al recuperar una entidad, también se recuperan las relacionadas si no estaban cargadas en memoria.
$\space$$\space$
### 2.2.Política lazy
Para evitar esas sobrecargas de memoria se aconseja usar una política lazy mediante el parámetro `fetch=FetchType.LAZY`.

Consiste en inicializar con un proxy las entidades correspondientes a los atributos anotados con `@xxxToOne`. Esto hace que inicialmente solo contengan la clave. Cuando se invoca una operación sobre el proxy diferente a getId este lanza una consulta para recuperar el valor del resto de atributos.

![[lazy eager.png]]

JPA usa por defecto la política lazy para relaciones `@xxxToMany`. Cuando se itera o se invoca una operación sobre la colección de valores se lanza una consulta para recuperar valores de las instancias relacionadas.