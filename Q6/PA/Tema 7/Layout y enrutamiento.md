[[Tema 7-Frontend de una tienda de comercio electrónico]]

## 1.Renderizado
El componente `App` se renderiza en `src/main.jsx`. Este componente define el layout de la interfaz.

### 1.1.App.jsx

```javascript
import {useEffect} from 'react';  
import {useDispatch} from 'react-redux';  
  
import Header from './Header';  
import Body from './Body';  
import Footer from './Footer';  
import users from '../../users';  
import catalog from '../../catalog';  
  
const App = () => {  
  
    const dispatch = useDispatch();  
  
    useEffect(() => {  
    
        dispatch(users.actions.tryLoginFromServiceToken(  
            () => dispatch(users.actions.logout())));  
  
        dispatch(catalog.actions.findAllCategories());  
  
    }, [dispatch]);  
  
    return (  
        <div>  
            <Header/>            
            <Body/>            
            <Footer/>        
        </div>    
    ); 
}  
  
export default App;
```

## 2.Enrutamiento
Para poder navegar entre pantallas el frontend utiliza una librería de enrutamiento mediante enlaces llamada React Router. Cambia la URL del navegador para que sea consistente con la pantalla que se muestra.

### 2.1.BrowserRouter
El componente `BrowseRouter` envuelve a `App` en el main. Funciona de forma similar al `Provider` de Redux. De esta forma proporciona información para enrutar todos los componentes del árbol.

```javascript
// src/main.jsx
const root = ReactDOM.createRoot(document.getElementById('root'));  
root.render(  
    <React.StrictMode>  
        <Provider store={store}>  
            <IntlProvider locale={locale} messages={messages}> 
                <BrowserRouter>                    
	                <App/>               
	             </BrowserRouter> 
	        </IntlProvider>        
	    </Provider>    
	</React.StrictMode>
);
```

### 2.2.Componente Link
El componente `Link` permite insertar un enlace a una pantalla. Funciona como la etiqueta `<a href=...>` de HTML. Por ejemplo:

```javascript
<li className="nav-item">  
    <Link className="nav-link" to="/shopping/find-orders-result">  
        <FormattedMessage id="project.shopping.header.orders"/>  
    </Link>
</li>
```

### 2.3.Componente Routes
El componente `Routes` funciona como una especie de estructura `switch-case` con los paths que se dan al cambiar de pantallas. Por ejemplo:

```javascript
<div className="container">  
    <br/>    
    <AppGlobalComponents/>   
    <Routes>        
	    <Route path="/*" element={<Home/>}/>  
        <Route path="/catalog/find-products-result" element={<FindProductsResult/>}/>  
        <Route path="/catalog/product-details/:id" element={<ProductDetails/>}/>  
        {loggedIn && <Route path="/shopping/shopping-cart" element={<ShoppingCart/>}/>}  
        {loggedIn && <Route path="/shopping/buy" element={<Buy/>}/>}  
        {loggedIn && <Route path="/shopping/purchase-completed" element={<PurchaseCompleted/>}/>}  
        {loggedIn && <Route path="/shopping/find-orders-result" element={<FindOrdersResult/>}/>}  
        {loggedIn && <Route path="/shopping/order-details/:id" element={<OrderDetails/>}/>}  
        {loggedIn && <Route path="/users/update-profile" element={<UpdateProfile/>}/>}  
        {loggedIn && <Route path="/users/change-password" element={<ChangePassword/>}/>}  
        {loggedIn && <Route path="/users/logout" element={<Logout/>}/>}  
        {!loggedIn && <Route path="/users/login" element={<Login/>}/>}  
        {!loggedIn && <Route path="/users/signup" element={<SignUp/>}/>}  
    </Routes>  
</div>
```

#### 2.3.1.Cambios de pantalla
Cuando se produce un cambio de pantalla se renderiza el Route cuyo path concuerde mejor y se muestra el componente especificado en él. 

Por ejemplo, cuando se llama a `/catalog/find-products-result` hay dos paths que concuerdan, el de `Home` y el de `FindProductsResult`. Como es más concreto el segundo, se carga ese componente.

#### 2.3.2.Parámetros
Los paths de Route pueden contener parámetros. Por ejemplo, el path del componente `ProductDetails`.

El parámetro `:id` renderiza el `ProductDetails` correspondiente al ID que se pase. Se puede acceder a este id mediante el hook `useParams()`.

```javascript
// ProductDetails.jsx
const {id} = useParams();  
  
useEffect(() => {  
  
    const productId = Number(id);  
  
    if (!Number.isNaN(productId)) {  
        dispatch(actions.findProductById(productId));  
    }  
  
    return () => dispatch(actions.clearProduct());  
  
}, [id, dispatch]);
```

