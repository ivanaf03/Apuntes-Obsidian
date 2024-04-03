[[Tema 6-Gestión de estado con Redux]]

## 1.Creación del store
Para crear el `store` utilizamos la función `configureStore` de la librería Redux Toolkit. Permite crear el objeto `store` y añade un conjunto de capacidades adicionales sobre Redux:
+ Integración con el plugin Redux DevTools
+ Integración con la librería ReduxThunk
+ Detección de modificaciones del estado

$\space$
Recibe un objeto que puede tener varios campos. Es obligatorio especificar el reductor.

```javascript
import React from 'react';
import ReactDOM from 'react-dom/client';
import {configureStore} from '@reduxjs/toolkit';
import {Provider} from 'react-redux';

import App from './App';
import './styles.css';
import reducer from './reducer';

/* Configure store. */
const store = configureStore({reducer});

/* Render application. */
const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(
    <React.StrictMode>
        <Provider store={store}>
            <App/>
        </Provider>
    </React.StrictMode>);
```

## 2.Suscripciones
El `useSelector` permite suscribir el componente al `store`. Recibe un selector como parámetro.

Un selector es una función pura que devuelve un valor a partir del estado almacenado en el `store`. Ocultan la estructura interna del estado a los componentes. La estructura interna solo afecta a la implementación de los selectores y del reductor, no afecta a los componentes.

```javascript
import { useSelector, useDispatch } from 'react-redux';
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

## 3.Acciones
Cuando se ejecuta una acción cada componente suscrito al store se vuelve a renderizar si alguno de los selectores devuelve un valor distinto al de la última vez. 

Para la comparación se usa `===`. Esto se asume porque el estado es inmutable.

```javascript
//actionTypes.js
export const increment = () => ({type: 'INCREMENT'});
export const decrement = () => ({type: 'DECREMENT'});
export const reset = () => ({type: 'RESET'});
```

```javascript
//reducer.js
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

