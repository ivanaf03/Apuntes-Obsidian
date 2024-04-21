[[Tema 7-Frontend de una tienda de comercio electrónico]]

## 1.Uncontrolled components
El componente `AddTodo` de los primeros ejemplos accedía a la entrada mediante el atributo `ref`. Los componentes que implementan formularios de este estilo se llaman uncontrolled components.

Los datos del formulario se guardan directamente en el DOM de la página. Para conocer los valores de los componentes hay que consultar directamente el DOM. 

### 1.1.Problemas
React no recomienda hacer esto:
+ [c] Parte del estado de la UI no se controla por React o Redux.
+ [c] Complica la implementación de funcionalidades adicionales.

## 2.Controlled components
Los componentes controlados se implementan con otro estilo. Los datos del formulario se guardan en el estado del componente. Los campos de entrada usan `value` y `onChange` para actualizar el estado.

### 2.1.Ventajas
Con respecto a los uncontrolled componentes, los controlled:
+ [p] Requieren algo más cantidad de código.
+ [p] Facilitan añadir funcionalidades.
+ [p] Muestran los datos en mayúscula. 

### 2.2.FindProducts

![[findProducts.png]]

```javascript
import {useState} from 'react';  
import {useDispatch} from 'react-redux';  
import {useNavigate} from 'react-router-dom';  
import {FormattedMessage} from 'react-intl';  
  
import CategorySelector from './CategorySelector';  
import * as actions from '../actions';  
  
const FindProducts = () => {  
  
    const dispatch = useDispatch();  
    const navigate = useNavigate();  
    const [categoryId, setCategoryId] = useState('');  
    const [keywords, setKeywords] = useState('');  
  
    const handleSubmit = event => {  
        event.preventDefault();  
        dispatch(actions.findProducts(  
            {categoryId: toNumber(categoryId),   
                keywords: keywords.trim(), page: 0}));  
        navigate('/catalog/find-products-result');  
    }  
  
    const toNumber = value => value.length > 0 ? Number(value) : null;  
  
    return (  
  
        <form className="form-inline mt-2 mt-md-0" onSubmit={e => handleSubmit(e)}>  
  
            <CategorySelector id="categoryId" className="custom-select my-1 mr-sm-2"  
                value={categoryId} onChange={e => setCategoryId(e.target.value)}/>  
  
            <input id="keywords" type="text" className="form-control mr-sm-2"  
                value={keywords} onChange={e => setKeywords(e.target.value)}/>  
            <button type="submit" className="btn btn-primary my-2 my-sm-0">  
                <FormattedMessage id='project.global.buttons.search'/>  
            </button>  
        </form>  
    );  
  
}  
  
export default FindProducts;
```

### 2.3.FindProductsResult

![[findproductsresult.png]]

```javascript
import {useSelector, useDispatch} from 'react-redux';  
import {FormattedMessage} from 'react-intl';  
  
import * as selectors from '../selectors';  
import * as actions from '../actions';  
import {Pager} from '../../common';  
import Products from './Products';  
  
const FindProductsResult = () => {  
  
    const productSearch = useSelector(selectors.getProductSearch);  
    const categories = useSelector(selectors.getCategories);  
    const dispatch = useDispatch();  
  
    if (!productSearch) {  
        return null;  
    }  
  
    if (productSearch.result.items.length === 0) {  
        return (  
            <div className="alert alert-danger" role="alert">  
                <FormattedMessage id='project.catalog.FindProductsResult.noProductsFound'/>  
            </div>        );  
    }  
      
    return (  
  
        <div>  
            <Products products={productSearch.result.items} categories={categories}/>  
            <Pagerback={{  
                    enabled: productSearch.criteria.page >= 1,  
                    onClick: () => dispatch(actions.previousFindProductsResultPage(productSearch.criteria))}}  
                next={{  
                    enabled: productSearch.result.existMoreItems,  
                    onClick: () => dispatch(actions.nextFindProductsResultPage(productSearch.criteria))}}/>  
        </div>  
    );  
  
}  
  
export default FindProductsResult;
```

### 2.4.Products

```javascript
import {FormattedMessage} from 'react-intl';  
import PropTypes from 'prop-types';  
  
import * as selectors from '../selectors';  
import {ProductLink} from '../../common';  
  
const Products = ({products, categories}) => (  
  
    <table className="table table-striped table-hover">  
  
        <thead>            <tr>                <th scope="col">  
                    <FormattedMessage id='project.global.fields.department'/>  
                </th>                <th scope="col">  
                    <FormattedMessage id='project.global.fields.name'/>  
                </th>            </tr>        </thead>  
        <tbody>            {products.map(product =>   
                <tr key={product.id}>  
                    <td>{selectors.getCategoryName(categories, product.categoryId)}</td>  
                    <td><ProductLink id={product.id} name={product.name}/></td>  
                </tr>            )}  
        </tbody>  
  
    </table>  
);  
  
Products.propTypes = {  
    products: PropTypes.array.isRequired,  
    categories: PropTypes.array.isRequired  
};  
  
export default Products;
```

## 3.Propiedades
En estos ejemplos se usa la librería `prop-types` para especificar las propiedades que se pasan a los componentes. Por ejemplo, `Products` recibe los productos y categorías.

```javascript
Products.propTypes = {  
    products: PropTypes.array.isRequired,  
    categories: PropTypes.array.isRequired  
};  
```

React verifica en tiempo de ejecución que el componente recibe los valores según se especifiquen y lanza un warning en caso contrario.

## 4.Acciones

```javascript
import * as actionTypes from './actionTypes';  
import * as selectors from './selectors';  
import backend from '../../backend';  
  
const findAllCategoriesCompleted = categories => ({  
    type: actionTypes.FIND_ALL_CATEGORIES_COMPLETED,  
    categories  
});   
  
export const findAllCategories = () => (dispatch, getState) => {  
  
    const categories = selectors.getCategories(getState());  
  
    if (!categories) {  
  
        backend.catalogService.findAllCategories(  
            categories => dispatch(findAllCategoriesCompleted(categories))  
        );  
          
    }  
  
}  
  
const findProductsCompleted = productSearch => ({  
    type: actionTypes.FIND_PRODUCTS_COMPLETED,  
    productSearch  
});  
  
export const findProducts = criteria => dispatch => {  
  
    dispatch(clearProductSearch());  
    backend.catalogService.findProducts(criteria,  
        result => dispatch(findProductsCompleted({criteria, result})));  
  
}  
  
export const previousFindProductsResultPage = criteria =>  
    findProducts({...criteria, page: criteria.page-1});  
  
export const nextFindProductsResultPage = criteria =>  
    findProducts({...criteria, page: criteria.page+1});  
  
const clearProductSearch = () => ({  
    type: actionTypes.CLEAR_PRODUCT_SEARCH  
});  
  
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

### 4.1.Acciones asíncronas
Cuando se realizan peticiones al backend se realizan peticiones asíncronas. El código que realiza las peticiones no se bloquea mientras espera la respuesta. 

#### 4.1.1.Comunicación con el reductor
Las acciones deben:
+ Avisar al reductor del comienzo de la petición.
+ Informar de que la petición terminó correctamente.
+ Informar de que la petición terminó en error.

### 4.2.HandleSubmit
Para implementar el `handleSubmit` utilizaremos Redux Thunk. Esta función se usa para manejar la lógica de envío de datos después de que un usuario completa y envía un formulario. Permite que un action creator devuelva funciones en lugar de objetos. 

## 5.Reductor

```javascript
import {combineReducers} from 'redux';  
  
import * as actionTypes from './actionTypes';  
  
const initialState = {  
    categories: null,  
    productSearch: null,  
    product: null  
};  
  
const categories = (state = initialState.categories, action) => {  
  
    switch (action.type) {  
  
        case actionTypes.FIND_ALL_CATEGORIES_COMPLETED:  
            return action.categories;  
  
        default:  
            return state;  
  
    }  
  
}  
  
const productSearch = (state = initialState.productSearch, action) => {  
  
    switch (action.type) {  
  
        case actionTypes.FIND_PRODUCTS_COMPLETED:  
            return action.productSearch;  
  
        case actionTypes.CLEAR_PRODUCT_SEARCH:  
            return initialState.productSearch;  
  
        default:  
            return state;  
  
    }  
  
}  
  
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
  
const reducer = combineReducers({  
    categories,  
    productSearch,  
    product  
});  
  
export default reducer;
```