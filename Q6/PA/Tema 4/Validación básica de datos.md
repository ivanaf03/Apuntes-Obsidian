[[Tema 4-Capa de servicios REST con Spring]]
$\space$
## 1.Enfoque
Se usan spring-web y la API estándar de validaciones de Java para realizar validaciones básicas de los datos recibidos en las peticiones HTTP. Por ejemplo, comprobar que se envían los datos obligatorios, que un valor está dentro de un rango, etc.

Esto evita mucha lógica en la capa modelo. Simplifica el código y no es ningún problema porque la capa modelo solo es accesible a través de la capa de servicios REST.
$\space$
### 1.1.Fuente de los datos
Los datos pueden venir de:
+ Variables en el path
+ Parámetros HTTP
+ Representaciones en el cuerpo de la petición
$\space$
## 2.Funcionamiento 
Spring-web valida conversiones de valores y la obligatoriedad de variables del path o de parámetros HTTP en base a los tipos Java de los parámetros correspondientes al hacer el mapeo.
$\space$
### 2.1.Ejemplo: POST https:// ... /shopping/shoppingcarts/abc/buy
Spring-web devuelve un error 400 porque `abc` no es un valor convertible al tipo `Long` que pide `ShoppingController.buy`. 

Si la conversión no puede puede hacer o falta un parámetro obligatorio se lanza un error 400 con un JSON en la respuesta significativo útil para el debug. No se presentan problemas para el usuario, ya que no teclea manualmente el ID del carrito.
$\space$
### 2.2.Validaciones más refinadas
Cuando las validaciones no son tan triviales, por ejemplo, comprobar que una String tiene n caracteres, se deben pasar los datos en el cuerpo de las peticiones. Se suelen dar en peticiones POST/PUT. Se mapean a un DTO y se especifican reglas de validación mediante la API Bean Validation.
$\space$
#### 2.2.1.Ejemplo de Bean Validation

```java
@PostMapping("/shoppingcarts/{shoppingCartId}/buy")
public Long buy(@RequestAttribute Long userId,
				@PathVariable Long shoppingCartId, 
				@Validated @RequestBody BuyParamsDto params) // uso de @Validated
    throws InstanceNotFoundException, PermissionException, EmptyShoppingCartException {
    ...
}
```

`@Validated` hace que spring-web utilice la API Bean Validation. Si se incumple alguna regla lanza una `MethodArgumentNotValidException`.

Las reglas de validación se anotan en los DTOs:

```java
public class BuyParamsDto {  

    private String postalAddress;  
    private String postalCode;  
    
    @NotNull  // no nulo
    @Size(min=1, max=200)  // entre 1 y 200 caracteres
public String getPostalAddress() {  
       return postalAddress;  
    }  
    
    public void setPostalAddress(String postalAddress) {  
       this.postalAddress = postalAddress.trim();  
    }  
    
    @NotNull  // no nulo
    @Size(min=1, max=20)  // entre 1 y 20 caracteres  
    public String getPostalCode() {  
       return postalCode;  
    }  
    
    public void setPostalCode(String postalCode) {  
       this.postalCode = postalCode.trim();  
    }  
}
```

