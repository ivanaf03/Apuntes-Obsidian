[[Tema 2-Capa acceso a datos con Spring y JPA]]

# 1.Modelado de relaciones
Se modelan relaciones 1:1, 1:N o N:M. Pueden ser unidireccionales o bidireccionales. Una relación es bidireccional cuando se puede navegar de la primera a la segunda y de la segunda a la primera.

Las relaciones N:M se suelen simplificar a relaciones 1:N con una entidad intermedia.

En un relación los lados actúan como:
+ [>] *Propietario:* entidad que contiene la clave foránea.
+ [>] *Inverso:* otro lado; solo en relaciones bidireccionales.

## 1.1.Relaciones 1:N
![[1N PA.png]]

```java
@Entity
@Table(name="OrderTable")
public class Order {
    // Otros atributos y métodos de la clase

    private Set<OrderItem> items = new HashSet<>();

    @OneToMany(mappedBy="order")
    public Set<OrderItem> getItems() {
        return items;
    }

    public void setItems(Set<OrderItem> items) {
        this.items = items;
    }

    // Otros atributos y métodos de la clase
}
```

```java
@Entity
public class OrderItem {
    // Otros atributos y métodos de la clase

    private Order order;

    @ManyToOne(optional=false, fetch=FetchType.LAZY)
    @JoinColumn(name="orderId")
    public Order getOrder() {
        return order;
    }

    public void setOrder(Order order) {
        this.order = order;
    }

    // Otros atributos y métodos de la clase
}
```

Los métodos get que permiten navegar de una entidad a otra llevan anotaciones `@ManyToOne` y `@OneToMany`. La primera se utiliza en el get del atributo con cardinalidad N y la segunda en del atributo con cardinalidad 1. Este último atributo suele usar Set para devolver la colección de entidades.

En relaciones bidireccionales se utiliza `mappedBy` en el lado inverso. Especifica el atributo del otro lado de la relación (nombre del método get sin get y la primera letra en minúscula, por ejemplo, getItem-->item).

La anotación `@JoinColumn` se coloca sobre el get de la entidad propietaria de la relación. En una relación 1:N el lado propietario siempre es el lado N. Especifica el nombre de la columna que actúa como clave foránea.

`optional=false` en `@ManyToOne` indica que getOrder nunca puede devolver nulos, es decir, que cada línea está asociada a un pedido obligatoriamente. En caso de `optional=true` la cardinalidad de Order sería 0...1. `@OneToMany` no tiene el parámetro optional porque si el pedido no tiene líneas de pedido asociadas devuelve un conjunto vacío, no devuelve nulos.

## 1.2.Relaciones 1:1
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

Es idéntico a las relaciones 1:N, pero usando `@OneToOne` en ambos lados. Permite también especificar `optional`.

## 1.3.Relaciones unidireccionales
![[relaciones unidireccionales.png]]

Cuando se modela una relación como unidireccional solo se anota el get del lado propietario, ya que no tienen lado inverso. No tendría sentido, por ejemplo, `category.getProducts()`, ya que podría devolver muchísimos productos de golpe.

# 2.Políticas de recuperación
Por ejemplo, para recuperar una instancia de BD de OrderItem podemos hacer `OrderItem item=entityManager.find(OrderItem.class, itemId)`. Esto haría:
1. Recuperaría la instancia de OrderItem haciendo un `select`.
2. Tendría que recuperar el producto y pedido asociados.
3. Como el producto tiene una categoría, tendría que recuperarla también.
4. Como el pedido tiene ítems y usuarios, tendría que recuperar todos los ítems del pedido y sus usarios asociados.
5. Así sucesivamente para cada ítem y usuario.

## 2.1.Política eager
JPA sigue una política eager. Si una entidad tiene una relación `@xxxToOne` con otra, al recuperar una entidad, también se recuperan las relacionadas si no estaban cargadas en memoria.

## 2.2.Política lazy
Para evitar esas sobrecargas de memoria se aconseja usar una política `lazy` mediante el parámetro `fetch=FetchType.LAZY`.

Consiste en inicializar con un proxy las entidades correspondientes a los atributos anotados con `@xxxToOne`. Esto hace que inicialmente solo contengan la clave. Cuando se invoca una operación sobre el proxy diferente a getId este lanza una consulta para recuperar el valor del resto de atributos.

![[lazy eager.png]]

JPA usa por defecto la política lazy para relaciones `@xxxToMany`. Cuando se itera o se invoca una operación sobre la colección de valores se lanza una consulta para recuperar valores de las instancias relacionadas.