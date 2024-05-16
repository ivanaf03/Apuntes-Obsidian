[[Tema 4-Capa de servicios REST con Spring]]
$\space$
## 1.Códigos de respuesta
Spring-web ofrece varias formas para que un método de un controlador devuelva un código de respuesta y una representación de este en el cuerpo:
+ **Si no devuelve excepción:** 200 OK y el valor en el cuerpo de la respuesta.
+ **Si devuelve una excepción:** código de la respuesta e información sobre el error.
$\space$
### 1.1.Excepciones
En PA Shop no se tratan las excepciones devueltas por los servicios locales en los controladores. Se declaran en el `throws` y se usan anotaciones para saber como tratar cada excepción.
$\space$
#### 1.1.1.Ejemplo 1

![[excepciones 1.png]]

```java
@ExceptionHandler(EmptyShoppingCartException.class)
@ResponseStatus(HttpStatus.NOT_FOUND)
@ResponseBody
public ErrorsDto handleEmptyShoppingCartException(EmptyShoppingCartException exception, Locale locale) {
    String errorMessage = messageSource.getMessage(EMPTY_SHOPPING_CART_EXCEPTION_CODE, null, EMPTY_SHOPPING_CART_EXCEPTION_CODE, locale);

    return new ErrorsDto(errorMessage);
}

@PostMapping("/shoppingcarts/{shoppingCartId}/addToShoppingCart")
public ShoppingCartDto addToShoppingCart(@RequestAttribute Long userId, @PathVariable Long shoppingCartId, @Validated @RequestBody AddToShoppingCartParamsDto params)
    throws InstanceNotFoundException, PermissionException, MaxQuantityExceededException, MaxItemsExceededException {  // controlada por @ExceptionHandler(EmptyShoppingCartException.class)
    
    return toShoppingCartDto(shoppingService.addToShoppingCart(userId, shoppingCartId, params.getProductId(), params.getQuantity()));
    
}
```

Por cada excepción se define un método que la trata con las anotaciones:
+ **@ExceptionHandler:** spring-web invoca al método cuando un controlador lance la excepción correspondiente.
+ **@ResponseStatus:** código de respuesta.
+ **@ResponseBody:** representación del contenido del cuerpo.
$\space$
#### 1.1.2.Ejemplo 2

![[excepciones 2.png]]

```java
@ControllerAdvice
public class CommonControllerAdvice {

...

	@ExceptionHandler(MethodArgumentNotValidException.class)
	@ResponseStatus(HttpStatus.BAD_REQUEST)
	@ResponseBody
	public ErrorsDto handleMethodArgumentNotValidException(MethodArgumentNotValidException exception) {
	    List<FieldErrorDto> fieldErrors = exception.getBindingResult().getFieldErrors().stream()
	            .map(error -> new FieldErrorDto(error.getField(), error.getDefaultMessage()))
	            .collect(Collectors.toList());
	
	    return new ErrorsDto(fieldErrors);
	}
...

}
```

La anotación `@ControllerAdvice` permite tratar las excepciones comunes a varios controladores en una única clase. Es un bean y permite utilizar inyección de dependencias sobre ella.

En el ejemplo anterior trata la excepción `MethodArgumentNotValidException` producida por incumplir una regla de validación en un parámetro anotado con `@Validated`.



