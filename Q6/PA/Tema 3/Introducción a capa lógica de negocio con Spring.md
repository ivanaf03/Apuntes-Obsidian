[[Tema 3-Capa lógica de negocio con Spring]]

# 1.Casos de uso
PA Shop ofrece 14 casos de uso, agrupados en 3 fachadas:
+ [>]  *UserService:* registro de usuarios.
+ [>] *CatalogService:* búsqueda de productos.
+ [>] *ShoppingService:* gestión del carrito, compra y pedidos.

$\space$
La implementación de estos servicios utiliza un servicio interno llamado `PermissionChecker`. Permite verificar los permisos de acceso, por ejemplo, de un usuario a un carrito.

```mermaid
classDiagram
class interface_UserService{
            + signUp(user: User) void
            + login(userName: String, password: String) User
            + loginFromId(id: Long) User
            + updateProfile(id: Long, firstName: String, lastName: String, email: String) User
            + changePassword(id: Long, oldPassword: String, newPassword: String) void
        }
```

```mermaid
classDiagram

class interface_CatalogService{
    + findAllCategories() List<Category>
    + findProductById(id : Long) Product
    + findProducts(categoryId : Long, keywords : String, page : int, size : int) Block_Product
}

class Block_Product {
    - items: List<Product>
    - existMoreItems : boolean
}

interface_CatalogService ..> Block_Product

```

```mermaid
classDiagram
class interface_ShoppingService{
    + addToShoppingCart(userId: Long, shoppingCartId: Long, productId: Long, quantity: int) : ShoppingCart
    + updateShoppingCartItemQuantity(userId: Long, shoppingCartId: Long, productId: Long, quantity: int) : ShoppingCart
    + removeShoppingCartItem(userId: Long, shoppingCartId: Long, productId: Long) : ShoppingCart
    + buy(userId: Long, shoppingCartId: Long, postalAddress: String, postalCode: String) : Order
    + findOrder(userId: Long, orderId: Long) : Order
    + findOrders(userId: Long, page: int, size: int) : Block<Order>
}
```


