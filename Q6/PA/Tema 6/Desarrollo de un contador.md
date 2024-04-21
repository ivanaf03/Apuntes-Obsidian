[[Tema 6-Gestión de estado con Redux]]

## 1.Creación de `store`
Para crear el `store` utilizamos la función `configureStore` de Redux Toolkit. Esta función crea el árbol y a mayores añade integración con Redux DevTools, con Redux Thunk y detecta modificaciones del estado. Recibe un objeto que puede tener varios campos, entre ellos el `reducer`.

### 1.1.Main.jsx

```javascript
import React from 'react';  
import ReactDOM from 'react-dom/client';  
import {configureStore} from '@reduxjs/toolkit'  
import {Provider} from 'react-redux'  
  
import App from './App';  
import reducer from './reducer';  
  

const store = configureStore({reducer});  
  
const root = ReactDOM.createRoot(document.getElementById('root'));  
root.render(  
    <React.StrictMode>  
        <Provider store={store}>  
            <App/> 
        </Provider>    
    </React.StrictMode>
);
```

## 2.Suscripciones
Con `useSelector` podemos suscribir un componente al `store`. Recibe un selector como parámetro.

### 2.1.App.jsx

```javascript
import {useSelector, useDispatch} from 'react-redux';  
  
import * as actions from './actions';  
import * as selectors from './selectors';  
  
const App = () => {  
  
    const value = useSelector(selectors.getValue);  
    const dispatch = useDispatch();  
  
    return (  
        <div>  
            {value + ' '}  
            <button onClick={() => dispatch(actions.increment())}>+</button>  
            {' '}  
            <button onClick={() => dispatch(actions.decrement())}>-</button>  
            {' '}  
            <button onClick={() => dispatch(actions.reset())}>Reset</button>  
        </div>    
    );  
  
}  
  
export default App;
```

### 2.2.Selectores en Redux
Un selector es una función pura que devuelve un valor a partir del estado almacenado. Permiten ocultar la estructura interna del estado a los componentes. 

La estructura interna solo se conoce en este ejemplo en `reducer.js` y en `selectors.js`. Si esta estructura interna varía, los componentes internos no se ven afectados.

#### 2.2.1.Reducer.js

```javascript
const reducer = (state={value: 0}, action) => {  
  
    switch(action.type) {  
        case 'INCREMENT':  
            return {value: state.value+1};  
        case 'DECREMENT':  
            return {value: state.value-1};  
        case 'RESET':  
            return {value: 0};  
        default:  
            return state;  
    }  
  
}  
  
export default reducer;
```

#### 2.2.2.Selectors.js

```javascript
export const getValue = state => state.value;
```

### 2.3.Acciones
Al ejecutar una acción el componente suscrito al `store` se vuelve a renderizar si algún selector devuelve un valor diferente al de la última vez. Utiliza comparación con igualdad referencial `===` y asume estado inmutable.

#### 2.3.1.Actions.js

```javascript
export const increment = () => ({type: 'INCREMENT'});  
export const decrement = () => ({type: 'DECREMENT'});  
export const reset = () => ({type: 'RESET'});
```

