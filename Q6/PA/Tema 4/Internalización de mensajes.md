[[Tema 4-Capa de servicios REST con Spring]]
$\space$
## 1.Mensajes de error
Los mensajes de error deben ir en el idioma que el usuario tenga seleccionado. La emisión de mensajes en un idioma concreto se denomina `i18n` o internacionalización. Se hace mediante locales, una abstracción de idioma, país y variante.
$\space$
### 1.1.Internacionalización en Java
En Java se puede usar `java.util.Locale`. Permite internacionalizar, además de los mensajes, las fechas, monedas, etc. 

En el backend solo se tratan los mensajes y se dejan para el frontend el resto de aspectos. Spring permite hacerlo mediante ficheros properties con el formato clave = mensaje en el idioma x. En PA Shop los mensajes se guardan en `backend/src/main/resources`.

Se usa el bean `MessageSource` para recuperar el mensaje a partir de su clave.
$\space$
### 1.2.Peticiones del navegador
Los navegadores pueden enviar en las peticiones HTTP la cabecera `Accept-Language`. Es una lista priorizada de los locales que prefiere el usuario. 
$\space$
### 1.3.Mensajes en otros idiomas
Algunos idiomas no están disponibles en la implementación de la API de Bean Validation. Por ejemplo, el gallego. Se deben definir en `messages_gl.properties`.
$\space$
## 2.Ejemplos
Veamos algunos ejemplos de internacionalización.
$\space$
### 2.1.Ejemplo 1

```java
public class ShoppingController {

    @Autowired  
    private MessageSource messageSource;

    @ExceptionHandler(EmptyShoppingCartException.class)  
    @ResponseStatus(HttpStatus.NOT_FOUND)  
    @ResponseBody  
    public ErrorsDto handleEmptyShoppingCartException(EmptyShoppingCartException exception, Locale locale) {  
        String errorMessage = messageSource.getMessage(EMPTY_SHOPPING_CART_EXCEPTION_CODE,  // mensaje
        null,  
        EMPTY_SHOPPING_CART_EXCEPTION_CODE,  // mensaje
        locale);  

        return new ErrorsDto(errorMessage);  
    }
}

// messages_en.properties project.exceptions.EmptyShoppingCartException=shopping cart is empty 

// messages_es.properties project.exceptions.EmptyShoppingCartException=el carrito está vacío

// messages_gl.properties project.exceptions.EmptyShoppingCartException=o carro está baleiro
```
$\space$
### 2.1.Ejemplo 2
Algunos mensajes contienen partes variables. El segundo parámetro de `messageSource.getMessage` permite pasar un array de valores para substituir en el mensaje. 

```java
@ExceptionHandler(InstanceNotFoundException.class)
@ResponseStatus(HttpStatus.NOT_FOUND)
@ResponseBody
public ErrorsDto handleInstanceNotFoundException(InstanceNotFoundException exception, Locale locale) {

    String nameMessage = messageSource.getMessage(exception.getName(), null, exception.getName(), locale);
    
    String errorMessage = messageSource.getMessage(INSTANCE_NOT_FOUND_EXCEPTION_CODE, new Object[] {nameMessage, exception.getKey().toString()}, INSTANCE_NOT_FOUND_EXCEPTION_CODE, locale);

    return new ErrorsDto(errorMessage);
}

// project.exceptions.InstanceNotFoundException={0} with identifier ''{1}'' not found
```







