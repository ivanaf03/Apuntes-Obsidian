[[Tema 3-Capa lógica de negocio con Spring]]
$\space$
## 1.Casos de uso
PA Shop ofrece 14 casos de uso agrupados en 3 servicios locales siguiendo el patrón fachada:
+ **UserService:** registro de usuarios.
+ **CatalogService:** búsqueda de productos.
+ **ShoppingService:** gestión del carrito, compra y visualización de pedidos.
$\space$
### 1.1.UserService

![[userservice.png]]

En `signUp` se devuelve el ID. Cuando se invoca a `signUp`, a `login` o a `updateProfile` el frontend cachea la información de usuario (excepto la contraseña por razones de seguridad). Cuando el usuario accede al perfil, los datos se recuperan de caché.

En la capa REST en `updateProfile` y en `changePassword` se evita que un usuario pase un id cualquiera.
$\space$
### 1.2.CatalogService

![[catalogservice.png]]

Para `findAllCategories` el frontend cachea el resultado para mostrar en un desplegable una lista de categorías. No tendría sentido usa paginación.
$\space$
### 1.3.ShoppingService

![[shoppingservice.png]]

El frontend cachea la información del carrito al invocar a `addToShoppingCart`, `updateShoppingCartItemQuantity` o `removeShoppingCartItem`. Cuando un usuario visualiza el carrito, este se recupera de caché.
$\space$
### 1.4.PermissionChecker
PA Shop utiliza otro servicio adicional interno llamado `PermissionChecker`. Permite verificar permisos de acceso. Por ejemplo, permite que un usuario solo pueda ver su propio carrito.

