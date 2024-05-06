[[Tema 2-Capa acceso a datos con Spring y JPA]]
$\space$
## 1.Entidades en PA Shop
Las entidades en PA Shop se muestran en el siguiente diagrama:

![[entidades PA.png]]
$\space$
### 1.1.Modelado de entidades
Una clase entidad se crea al anotarla con `@Entity`. Necesita un constructor sin argumentos `public` o `protected`. No puede ser `final`. Necesita un atributo que actúa como clave primaria y permite relaciones de herencia o asociación con otras entidades.
$\space$
#### 1.1.1.Estado persistente
Las entidades de Hibernate tienen estado persistente. Estos son el conjunto de atributos de la clase que se mapearán en columnas. Son de tipos Java que tengan equivalencias en SQL:
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
$\space$
#### 1.1.2.Acceso al estado
El mapeador objeto-relacional puede acceder al estado persistente, o lo que es lo mismo, a las propias tablas, de dos formas:
+ **Tipo de acceso campo:** se accede a través de los atributos.
+ **Tipo de acceso propiedad:** se accede mediante getter y setter. Usaremos este tipo.
$\space$
### 1.2.Anotaciones de Hibernate
Para mapear mediante anotaciones se usa:
+ **@Table:** por defecto una entidad se mapea a una tabla con el mismo nombre simple de la clase. Si queremos un nombre distinto debemos usar esta anotación.
+ **@Column:** cada atributo se mapea a una columna con el mismo nombre. Cuando queremos un nombre distinto debemos usar esta anotación.
+ **@Id:** especifica el atributo clave primaria. Sólo sirve para claves simples, aunque existen anotaciones para claves compuestas.
+ **@GeneratedValue:** se puede usar con `@Id` si la clave es numérica y queremos que se genere automáticamente. `GenerationType.IDENTITY` asume que la tabla usa columnas contador. Si se usase una secuencia usaríamos `GenerationType.SEQUENCE` con `@SequenceGenerator`.
$\space$
#### 1.2.1.Ejemplo de anotaciones en la clase Order

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
  
...

}
```
$\space$
## 2.Patrón Domain Model
Las entidades a veces contienen métodos de negocio que puedan facilitar la implementación de capas superiores. Esto se conoce como patrón Domain Model.

Si uno de estos métodos empieza por get o is debemos decirle al mapeador que no es una entidad persistente. Esto se hace con `@Transient`.

```java
public class ShoppingCartItem {

	...

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