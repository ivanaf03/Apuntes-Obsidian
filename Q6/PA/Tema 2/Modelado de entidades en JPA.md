[[Tema 2-Capa acceso a datos con Spring y JPA]]

# 1. Diagrama de entidades en PA Shop
![[entidades PA.png]]
No sería necesario indicar, por ejemplo, el user en Order (queda indicado con la relación).

# 2. Modelado de entidades
Las clases entidad se anotan con `@Entity`. Deben tener un constructor sin argumentos `public` o `protected`. Debe tener clave primaria. Puede tener relaciones de herencia o asociación. Tienen estado persistente.

## 2.1. Estado persistente
El estado persistente de una clase son el conjunto de atributos que se mapearán en columnas. Son de tipos de Java de los cuales existe una equivalencia en SQL:
+ [>] String
+ [>] BigInteger
+ [>] BigDecimal
+ [>] byte\[]
+ [>] Byte\[]
+ [>] char\[]
+ [>] Character\[]
+ [>] LocalDate
+ [>] LocalDateTime
+ [>] Enumerados (se mapean a un tipo SQL numérico)
+ [>] Entidades y colecciones de entidades (se mapean en relaciones)

El mapeador objeto-relacional puede acceder al estado persistente:
+ [>] *Tipo de acceso campo:* a través de los atributos.
+ [>] *Tipo de acceso propiedad:* mediante getter y setter.

## 2.2. Anotaciones
Para mapear mediante anotaciones podemos usar:
+ *@Table:* por defecto una entidad se mapea a una tabla con el mismo nombre simple de la clase. Si queremos un nombre distinto debemos usar `@Table`.
+ *@Column:* cada atributo o propiedad persistente se mapea a una columna con el mismo nombre. Cuando queremos un nombre distinto usamos `@Column`.
+ *@Id:* especifica el atributo clave. Sólo sirve para claves simples, aunque hay anotaciones para claves compuestas.
+ *@GeneratedValue:* se puede usar con `@Id` si la clave es numérica y queremos que se genere automáticamente. `GenerationType.IDENTITY` asume que la tabla usa columnas contador. Si se usase una secuencia usaríamos `GenerationType.SEQUENCE` con `@SequenceGenerator`.

# 3. Ejemplo: Order
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

# 4. Métodos de negocio en entidades
Las entidades a veces contienen métodos de negocio que puedan facilitar la implementación de capas superiores. Esto se conoce como patrón Domain Model.

Si uno de estos métodos empieza por get o is debemos decirle al mapeador que no es una entidad persistente. Esto se hace con `@Transient`.

```java
public class ShoppingCartItem {
    // Otros campos y métodos de la clase...

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