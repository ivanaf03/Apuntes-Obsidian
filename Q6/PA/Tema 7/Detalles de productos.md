[[Tema 7-Frontend de una tienda de comercio electrónico]]
$\space$
## 1.Componentes
El enlace que aparece como resultado de cada producto que aparece al hacer una búsqueda se muestra desde `Products` con `ProductLink id={product.id} name={product.name}`.
$\space$
### 1.1.ProductLink

```javascript
import PropTypes from 'prop-types';  
  
import {Link} from 'react-router-dom';  
  
const ProductLink = ({id, name}) => {  
      
    return (  
        <Link to={`/catalog/product-details/${id}`}>  
            {name}  
        </Link>  
    );  
  
}  
  
ProductLink.propTypes = {  
    id: PropTypes.number.isRequired,  
    name: PropTypes.string.isRequired,  
};  
  
export default ProductLink;
```

Cuando un usuario presiona sobre el nombre de un producto se renderiza `ProductDetails`. En el `Body` el React Router enruta `/catalog/product-details/:id` con `ProductDetails`.
$\space$
### 1.2.ProductDetails

```javascript
import {useEffect} from 'react';  
import {useSelector, useDispatch} from 'react-redux';  
import {FormattedMessage, FormattedNumber} from 'react-intl';  
import {useParams} from 'react-router-dom';  
  
import users from '../../users';  
import * as selectors from '../selectors';  
import * as actions from '../actions';  
import {AddToShoppingCart} from '../../shopping';  
import {BackLink} from '../../common';  
  
const ProductDetails = () => {  
  
    const loggedIn = useSelector(users.selectors.isLoggedIn);  
    const product = useSelector(selectors.getProduct);  
    const categories = useSelector(selectors.getCategories);  
    const dispatch = useDispatch();  
    const {id} = useParams();  
  
    useEffect(() => {  
  
        const productId = Number(id);  
  
        if (!Number.isNaN(productId)) {  
            dispatch(actions.findProductById(productId));  
        }  
  
        return () => dispatch(actions.clearProduct());  
  
    }, [id, dispatch]);  
  
    if (!product) {  
        return null;  
    }  
          
    return (  
  
        <div>  
  
            <BackLink/>            <div className="card text-center">  
                <div className="card-body">  
                    <h5 className="card-title">{product.name}</h5>  
                    <h6 className="card-subtitle text-muted">  
                        <FormattedMessage id='project.global.fields.department'/>:&nbsp;  
                            {selectors.getCategoryName(categories, product.categoryId)}  
                    </h6>  
                    <p className="card-text">{product.description}</p>  
                    <p className="card-text font-weight-bold">  
                        <FormattedMessage id='project.global.fields.price'/>{': '}  
                        <FormattedNumber value={product.price} style="currency" currency="EUR"/>  
                    </p>                </div>            </div>  
            {loggedIn &&   
                <div>  
                    <br/>                    <AddToShoppingCart productId={product.id}/>  
                </div>            }  
  
        </div>  
  
    );  
  
}  
  
export default ProductDetails;
```

Cuando se carga en producto en detalle en el Virtual DOM no se muestra nada. Después se lanza la acción `actions.findProductById` que hace una petición al backend para obtener los datos del producto y actualizar el estado de Redux.

El componente se vuelve a renderizar y muestra los datos del producto. Cuando el usuario cambie de pantalla los detalles desaparecerán del Virtual DOM. Para que ocurra lo mismo en cada renderización se lanza la acción `actions.clearProduct`.
$\space$
#### 1.2.1.UseEffect
Es un hooks que recibe el efecto y las dependencias.

El efecto es una función que se ejecuta después de cada renderización del componente. Puede devolver una función llamada clean-up. Después de que el componente se monte en el Virtual DOM por primera vez se produce el efecto. Después de cada renderización se ejecuta el clean-up y el efecto si sigue montado en el Virtual DOM. Antes de que el componente se desmonte se ejecuta el clean up.

El segundo argumento son las dependencias. Es un array opcional de valores que permite ejecutar opcionalmente el clean-up y el efecto. Si no se pasan las dependencias siempre se ejecutan tras cada nueva renderización. Si se pasa un array vacío nunca se ejecuta. Si se pasa un array con dependencias, solo se ejecutará cuando los valores recibidos sean diferentes a los de la última vez que se ejecutó el efecto.

En este caso, cuando el componente se monta en el Virtual DOM el componente no muestra nada porque el producto es nulo. Tras esa renderización se ejecuta el efecto y se lanza la búsqueda del producto al backend. Esto provoca un cambio de estado, por lo que el componente se vuelve a renderizar mostrando los datos del producto. Como los valores de las dependencias no cambian no se ejecuta el clean-up y el efecto.  Cuando el usuario cambia de pantalla `ProductDetails` se desmonta del Virtual DOM.

En este caso concreto no son necesarias las dependencias. Sin embargo, se hace para evitar los warnings producidos por `npm run lint`.
 $\space$
## 2.Acciones

```javascript
const findProductByIdCompleted = product => ({  
    type: actionTypes.FIND_PRODUCT_BY_ID_COMPLETED,  
    product  
});  
      
export const findProductById = id => dispatch => {  
    backend.catalogService.findByProductId(id,  
        product => dispatch(findProductByIdCompleted(product)));  
}  
  
export const clearProduct = () => ({  
    type: actionTypes.CLEAR_PRODUCT  
});
```
$\space$
## 3.Reductor

```javascript
const product = (state = initialState.product, action) => {  
  
    switch (action.type) {  
  
        case actionTypes.FIND_PRODUCT_BY_ID_COMPLETED:  
            return action.product;  
  
        case actionTypes.CLEAR_PRODUCT:  
            return initialState.product;  
  
        default:  
            return state; 
    }  
}
```
$\space$
## 4.StrictMode
Al utilizar `StrictMode` en modo desarrollo cuando se desmonta un componente, se desmonta y se vuelve a montar con efecto y clean up. Esto hace que se ejecute la petición GET dos veces. 

Pero esto solo ocurre en modo desarrollo.