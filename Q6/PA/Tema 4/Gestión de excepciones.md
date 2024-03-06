[[Tema 4-Capa de servicios REST con Spring]]

# 1.Códigos de respuesta
Existen varios mecanismos de Spring-web para que un método de un controlador devuelva un código de respuesta y una representación en el cuerpo de respuesta. Puede devolver:
+ [>] *Si no devuelve excepción:* 200 OK y la representación del valor en el cuerpo de la respuesta.
+ [>] *Si devuelve una excepción:* el código de la respuesta e información sobre el error.

## 1.1.Excepciones
No se tratan las excepciones devueltas por los métodos de los servicios locales. Se declaran en el `throws` de los métodos de los controladores. Se usan anotaciones para especificar como tratar cada excepción.

### 1.1.1.Ejemplo 1

![[excepciones 1.png]]

```java
@ExceptionHandler(EmptyShoppingCartException.class)  
@ResponseStatus(HttpStatus.NOT_FOUND)  
@ResponseBody  
public ErrorsDto handleEmptyShoppingCartException(EmptyShoppingCartException exception, Locale locale) {  
      
    String errorMessage = messageSource.getMessage(EMPTY_SHOPPING_CART_EXCEPTION_CODE, null,  
       EMPTY_SHOPPING_CART_EXCEPTION_CODE, locale);  
  
    return new ErrorsDto(errorMessage);  
      
}

@PostMapping("/shoppingcarts/{shoppingCartId}/addToShoppingCart")  
public ShoppingCartDto addToShoppingCart(@RequestAttribute Long userId, @PathVariable Long shoppingCartId,   
    @Validated @RequestBody AddToShoppingCartParamsDto params)   
    throws InstanceNotFoundException, PermissionException, MaxQuantityExceededException, MaxItemsExceededException {  
      
    return toShoppingCartDto(shoppingService.addToShoppingCart(userId, shoppingCartId, params.getProductId(),  
       params.getQuantity()));  
      
}
```

Las excepciones específicas a un controlador se tratan en el controlador. Por cada excepción se define un método que la trata. Se anotan con:
+ [>] *@ExceptionHandler:* Spring-web invoca al método cuando uno de los métodos del controlador lance la excepción especificada.
+ [>] *@ResponseStatus:*  código de estado de la respuesta.
+ [>] *@ResponseBody:* la representación del valor de retorno del método se usará como contenido del cuerpo.

### 1.1.2.Ejemplo 2

![[excepciones 2.png]]

```java
@ExceptionHandler(MethodArgumentNotValidException.class)  
@ResponseStatus(HttpStatus.BAD_REQUEST)  
@ResponseBody  
public ErrorsDto handleMethodArgumentNotValidException(MethodArgumentNotValidException exception) {  
            
    List<FieldErrorDto> fieldErrors = exception.getBindingResult().getFieldErrors().stream()  
       .map(error -> new FieldErrorDto(error.getField(), error.getDefaultMessage())).collect(Collectors.toList());  
      
    return new ErrorsDto(fieldErrors);  
      
}
```

Para tratar excepciones comunes a varios controladores podemos usar una clase anotada con `@ControllerAdvice`. Spring instancia la clase y genera un bean, por tanto se puede usar inyección de dependencias sobre ella con `@Autowired`.