[[Tema 7-Frontend de una tienda de comercio electrónico]]
$\space$
## 1.Peticiones HTTP
El ejemplo proporciona la función `appFetch`. Recibe un path, el tipo de petición HTTP, una función que se ejecutará en caso de que la respuesta sea exitosa y una función que se ejecutará en caso de que sea errónea. Si recibe un error 500 esta función despliega una ventana de error.

Además envía el token del usuario se se había autenticado antes.
$\space$
### 1.1.Ejemplos
Veamos algunos ejemplos de procesamiento de peticiones.
$\space$
#### 1.1.1.Ejemplo 1

```javascript
appFetch('/catalog/products?keywords=2001', config('GET'), result => doSomethingWithResult(result));

// HTTP/1.1 200 OK

/*
{ items: [ { id: 1, name: "2001: A Space Odyssey [Blu-ray]", categoryId: 1 } ], existMoreItems: false }
*/
```
$\space$
#### 1.1.2.Ejemplo 2

```javascript
appFetch('/catalog/products?keywords=2001', config('GET'), result => doSomethingWithResult(result));

// HTTP/1.1 200 OK

/*
12
*/
```
$\space$
#### 1.1.3.Ejemplo 3

```javascript
appFetch('/shopping/shoppingcarts/1/buy', config('POST', {postalAddress: "Rue del Percebe, 13", ...}), result => doSomethingWithResult(result), errors => doSomethingWithErrors(errors));

// HTTP/1.1 404 Not found

/*
{ globalError: "shopping cart is empty" }
*/
```
$\space$
#### 1.1.4.Ejemplo 4

```javascript
appFetch('/shopping/shoppingcarts/1/buy', config('POST', {postalAddress: "Rue del Percebe, 13", ...}), result => doSomethingWithResult(result), errors => doSomethingWithErrors(errors));

// HTTP/1.1 400 Bad request

/*
{ fieldErrors: [ { fieldName: "postalCode", message: "size must be between 1 and 20" } ] }
*/
```
$\space$
## 2.Diseño
En `src/backend` se define un fichero JavaScript por cada controlador REST con sus funciones respectivas. Por ejemplo:

```javascript
export const findProducts = ({categoryId, keywords, page},   
    onSuccess) => {  
  
    let path = `/catalog/products?page=${page}`;  
  
    path += categoryId ? `&categoryId=${categoryId}` : "";  
    path += keywords.length > 0 ? `&keywords=${encodeURIComponent(keywords)}` : "";  
  
    appFetch(path, config('GET'), onSuccess);  
  
}
```
$\space$
### 2.1.Impotación
En `src/backend/index.js` se importan las funciones de acceso a servicio.

```javascript
import {init} from './appFetch';  
import * as userService from './userService';  
import * as catalogService from './catalogService';  
import * as shoppingService from './shoppingService';  
  
export {default as NetworkError} from "./NetworkError";  
  
export default {init, userService, catalogService, shoppingService};
```

