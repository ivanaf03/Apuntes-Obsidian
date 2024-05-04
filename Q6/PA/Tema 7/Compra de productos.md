[[Tema 7-Frontend de una tienda de comercio electrónico]]

## 1.Componentes
### 1.1.Buy

```javascript
import {useSelector} from 'react-redux';  
  
import ShoppingItemList from './ShoppingItemList';  
import BuyForm from './BuyForm';  
import * as selectors from '../selectors';  
  
const Buy = () => {  
  
    const cart = useSelector(selectors.getShoppingCart);  
  
    if (cart.items.length === 0) {  
        return null;  
    }    return (  
        <div>  
            <BuyForm shoppingCartId={cart.id}/>  
            <ShoppingItemList list={cart}/>  
        </div>  
    );  
}  
  
export default Buy;
```

### 1.2.BuyForm

```javascript
import {useState} from 'react';  
import {useDispatch} from 'react-redux';  
import {FormattedMessage} from 'react-intl';  
import {useNavigate} from 'react-router-dom';  
import PropTypes from 'prop-types';  
  
import {Errors} from '../../common';  
import * as actions from '../actions';  
  
const BuyForm = ({shoppingCartId}) => {  
  
    const dispatch = useDispatch();  
    const navigate = useNavigate();  
    const [postalAddress, setPostalAddress] = useState('');  
    const [postalCode, setPostalCode] = useState('');  
    const [backendErrors, setBackendErrors] = useState(null);  
    let form;  
  
    const handleSubmit = event => {  
  
        event.preventDefault();  
  
        if (form.checkValidity()) {  
  
            dispatch(actions.buy(shoppingCartId,   
postalAddress.trim(), postalCode.trim(),   
() => navigate('/shopping/purchase-completed'),  
                errors => setBackendErrors(errors)));  
  
        } else {  
            setBackendErrors(null);  
            form.classList.add('was-validated');  
        }  
    }  
    return (  
  
        <div>  
            <Errors errors={backendErrors}  
                onClose={() => setBackendErrors(null)}/>  
            <div className="card bg-light border-dark">  
                <h5 className="card-header">  
                    <FormattedMessage id="project.shopping.BuyForm.title"/>  
                </h5>  
                <div className="card-body">  
                    <form ref={node => form = node}  
                        className="needs-validation" noValidate   
                        onSubmit={(e) => handleSubmit(e)}>  
                        <div className="form-group row">  
                            <label htmlFor="postalAddress" className="col-md-3 col-form-label">  
                                <FormattedMessage id="project.global.fields.postalAddress"/>  
                            </label>  
                            <div className="col-md-4">  
                                <input type="text" id="postalAddress" className="form-control"  
                                    value={postalAddress}  
                                    onChange={e => setPostalAddress(e.target.value)}  
                                    autoFocus  
                                    required/>  
                                <div className="invalid-feedback">  
                                    <FormattedMessage id='project.global.validator.required'/>  
                                </div>  
                            </div>  
                        </div>  
                        <div className="form-group row">  
                            <label htmlFor="postalCode" className="col-md-3 col-form-label">  
                                <FormattedMessage id="project.global.fields.postalCode"/>  
                            </label>  
                            <div className="col-md-4">  
                                <input type="text" id="postalCode" className="form-control"  
                                    value={postalCode}  
                                    onChange={e => setPostalCode(e.target.value)}  
                                    required/>  
                                <div className="invalid-feedback">  
                                    <FormattedMessage id='project.global.validator.required'/>  
                                </div>  
                            </div>  
                        </div>  
                        <div className="form-group row">  
                            <div className="offset-md-3 col-md-1">  
                                <button type="submit" className="btn btn-primary">  
                                    <FormattedMessage id="project.global.buttons.buy"/>  
                                </button>  
                            </div>  
                        </div>  
                    </form>  
                </div>  
            </div>  
        </div>  
  
    );  
}  
  
BuyForm.propTypes = {  
    shoppingCartId: PropTypes.number.isRequired  
};  
  
export default BuyForm;-*
```

### 1.3.Validaciones del lado cliente
Se usan las validaciones para formularios de HTML5. Se puede usar de dos formas:
+ Enfoque declarativo
+ Enfoque programático

#### 1.3.1.Enfoque declarativo
Los campos indican las restricciones que se deben cumplir. Algunas ya van implícitas con el tipo del campo:

```javascript
<input type='email' id=email>

//Crea automáticamente una restricción para validar que el valor introducido sigue la sintaxis de un correo electrónico.
```

Otras restricciones se pueden añadir a mayores:

```javascript
<input type="text" id="name" required minlength="6"
maxlength="20">

<input type="number" id="age" min="18" max="100">
```

La ventaja es que no hay que programar, pero esto también tiene sus desventajas:
+ [c] No hay un estándar para los mensajes de error.
+ [c] Los mensajes se muestran de acuerdo al locale del navegador, no de la aplicación.

#### 1.3.2.Enfoque programático
Funciona de formula similar al enfoque declarativo, permite especificar restricciones en los campos de entrada, pero el navegador no ejecuta las validaciones automáticamente. En su lugar, proporciona una API para ejecutar las validaciones y permite añadir mensajes de error con contenido propio.



## 2.Acciones

## 3.Reductor