[[Tema 2-Capa acceso a datos con Spring y JPA]]

## Diagrama de entidades en PA Shop
![[entidades PA.png]]
No sería necesario indicar, por ejemplo, el user en Order (queda indicado con la relación).

## Modelado de entidades
Las clases entidad se anotan con `@Entity`. Deben tener un constructor sin argumentos `public` o `protected`. Debe tener clave primaria. Puede tener relaciones de herencia o asociación.

### Estado persistente
El estado persistente de una clase son el conjunto de atributos que se mapearán en columnas. Son de tipos de Java de los cuales existe una equivalencia en SQL:
+ String
+ BigInteger
+ BigDecimal
+ byte\[]
+ Byte\[]
+ char\[]
+ Character\[]
+ LocalDate
+ LocalDateTime
+ Enumerados (se mapean a un tipo SQL numérico)
+ Entidades y colecciones de entidades (se mapean en relaciones)

El mapeador objeto-relacional puede acceder a los atributos:
+ **Tipo campo:** a través de los atributos.
+ **Tipo propiedad:** mediante getter y setter.

## Ejemplo: Order
![[tabla Order.png]]
```java
@Entity  
@Table(name = "OrderTable")  
public class Order {  
  
    public static final int MAX_ITEMS = 20;  
  
    private Long id;  
    private Set<OrderItem> items = new HashSet<>();  
    private User user;  
    private LocalDateTime date;  
    private String postalAddress;  
    private String postalCode;  
  
    public Order() {  
    }  
  
    public Order(User user, LocalDateTime date, String postalAddress, String postalCode) {  
  
        this.user = user;  
        this.date = date;  
        this.postalAddress = postalAddress;  
        this.postalCode = postalCode;  
  
    }  
  
    @Id  
    @GeneratedValue(strategy = GenerationType.IDENTITY)  
    public Long getId() {  
        return id;  
    }  
  
    public void setId(Long id) {  
        this.id = id;  
    }  
  
    @OneToMany(mappedBy = "order")  
    public Set<OrderItem> getItems() {  
        return items;  
    }  
  
    public void setItems(Set<OrderItem> items) {  
        this.items = items;  
    }  
  
    @ManyToOne(optional = false, fetch = FetchType.LAZY)  
    @JoinColumn(name = "userId")  
    public User getUser() {  
        return user;  
    }  
  
    public void setUser(User user) {  
        this.user = user;  
    }
    
    ...
}
```

### Anotaciones
+ **@Table:** Por defecto una entidad se mapea a una tabla con el mismo nombre simple de la clase. Si queremos un nombre distinto debemos usar `@Table`.
+ **@Column:** Cada atributo o propiedad persistente se mapea a una columna con el mismo nombre. Cuando queremos un nombre distinto usamos `@Column`.
+ **@Id:** Especifica el atributo propiedad/clave. Sólo sirve para claves simples, aunque hay anotaciones para claves compuestas.
+ **@GeneradesValue:** Se puede usar con `@Id` si la clave es numérica y queremos que se genere automáticamente. `GenerationType.IDENTITY` asume que la tabla usa columnas contador. Si se usase una secuencia usaríamos `GenerationType.SEQUENCE` con `@SequenceGenerator`.

## Relaciones 1:N
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

Los métodos get que permiten navegar de una entidad a otra llevan anotaciones `@ManyToOne` y `@OneToMany`. La primera se utiliza en el atributo con cardinalidad N y la segunda en el atributo con cardinalidad 1. Este último atributo suele usar Set para devolver la colección de entidades porque no suele importar el orden.

En relaciones bidireccionales se utiliza `mappedBy` en el lado inverso. Especifica el atributo/propiedad del otro lado de la relación (nombre del método get sin get y la primera letra en minúscula, por ejemplo, getItem-->item).

La anotación `@JoinColumn` se coloca sobre el get de la entidad propietaria de la relación. En una relación 1:N el lado propietario siempre es el lado N. Especifica el nombre de la columna que actúa como clave foránea.

`optional=false` en `@ManyToOne` indica que getOrder nunca puede devolver nulos, es decir, que cada línea está asociada a un pedido obligatoriamente. En caso de que `optional=true` la cardinalidad de Order sería 0...1. `@OneToMany` no tiene optional porque si el pedido no tiene líneas de pedido asociadas devuelve un conjunto vacío, no devuelve nulos.

## Relaciones 1:1
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

Es idéntico a las relaciones 1:N, pero con `@OneToOne` en ambos lados. Permite también especificar `optional`.

## Relaciones unidireccionales


## Métodos de negocio 
Las entidades pueden tener métodos de negocio para facilitar la implementación de capas superiores. Este patrón se llama Domain Model. 

Si el nombre de uno de estos métodos no empieza por get/is debemos anotarlo con `@Transient` para decirle al mapeador que no es un propiedad persistente.
```java
public class ShoppingCartItem {
    // Otros atributos y métodos de la clase

    public void incrementQuantity(int increment) throws MaxQuantityExceededException {
        if (quantity + increment > MAX_QUANTITY) {
            throw new MaxQuantityExceededException(MAX_QUANTITY - quantity);
        }
        this.quantity += increment;
    }

    @Transient
    public BigDecimal getTotalPrice() {
        return product.getPrice().multiply(new BigDecimal(quantity));
    }
}
```

