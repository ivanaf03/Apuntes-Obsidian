[[Tema 7-Frontend de una tienda de comercio electrónico]]

## 1.Estructura de Vite
El frontend de PA-Shop está hecho con la plantilla de Vite. En la carpeta `src` tenemos:
+ **backend:** capa de acceso a servicios.
+ **i18n:** internacionalización.
+ **modules:** capa UI.
+ **store:** creación del `store`.
+ **main.jsx:** creación de la aplicación.

## 2.Desarrollo multimodular
Dentro de la carpeta `modules` tenemos cada uno de los módulos que conforman la UI correspondiente a los controladores con el mismo nombre. Además contiene otros dos módulos:
+ **app:** layout de la UI.
+ **common:** componentes reusables.

### 2.1.Estructura de un módulo
Cada módulo es una parte de la UI. Un módulo está formado por los componentes, ficheros JavaScript para las acciones, reductores y selectores y un `index.js`, que define lo que se exportará a otros módulos.

#### 2.1.1.Exportación
En `index.js` tenemos los componentes que se exportan a otros módulos. Por ejemplo, para el del catálogo:

```javascript
import * as actions from './actions';  
import * as actionTypes from './actionTypes';  
import reducer from './reducer';  
import * as selectors from './selectors';  
  
export {default as FindProducts} from './components/FindProducts';  
export {default as FindProductsResult} from './components/FindProductsResult';  
export {default as ProductDetails} from './components/ProductDetails';  
  
export default {actions, actionTypes, reducer, selectors};
```

Por comodidad siempre se exportan las acciones, reductores reductores y selectores.

## 3.Reductor raíz
En `store/rootReducer.js` hay un reductor raíz que combina los reductores de los módulos.

```javascript
import {combineReducers} from 'redux';  
  
import app from '../modules/app';  
import users from '../modules/users';  
import catalog from '../modules/catalog';  
import shopping from '../modules/shopping';  
  
const rootReducer = combineReducers({  
    app: app.reducer,  
    users: users.reducer,  
    catalog: catalog.reducer,  
    shopping: shopping.reducer  
});  
  
export default rootReducer;
```

