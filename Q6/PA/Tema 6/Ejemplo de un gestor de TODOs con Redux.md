[[Tema 6-Gestión de estado con Redux]]
$\space$
## 1.Iteración 1-Crear un gestor de TODOs y que permita cambiar su estado
$\space$
### 1.1.App.jsx

```javascript
import AddTodo from './AddTodo';  
import Todos from './Todos';  
  
const App = () => (  
    <div>  
        <AddTodo/>        
        <Todos/>    
    </div>
);  
  
export default App;
```
$\space$
### 1.2.AddTodo.jsx

```javascript
import {useDispatch} from 'react-redux';  
  
import * as actions from './actions';  
  
const AddTodo = () => {  
  
    const dispatch = useDispatch();  
    let input;  
  
    return (  
        <form onSubmit={(e) => {  
                e.preventDefault();  
                if (!input.value.trim()) {  
                    return;  
                }  
                dispatch(actions.addTodo(input.value.trim()));  
                input.value = '';  
            }}>   
            <input type="text" ref={node => input = node}/>  
            <button type="submit">Add</button>   
        </form>  
    );  
}  
  
export default AddTodo;
```
$\space$
### 1.3.Todos.jsx

```javascript
import {useSelector, useDispatch} from 'react-redux';  
  
import Todo from './Todo';  
import * as actions from './actions';  
import * as selectors from './selectors';  
  
const Todos = () => {  
  
    const todos = useSelector(selectors.getVisibleTodos);  
    const dispatch = useDispatch();  
      
    return (  
        <ul>  
            {todos.map(todo =>   
                <Todo key={todo.id} todo={todo}  
                    onToggleCompleted={id => dispatch(actions.toggleTodo(id))}/>)  
            }  
        </ul>  
    );  
  
}  
  
export default Todos;
```
$\space$
### 1.4.ActionTypes.js

```javascript
export const ADD_TODO = 'ADD_TODO';  
export const TOGGLE_TODO = 'TOGGLE_TODO';
```
$\space$
### 1.5.Actions.js

```javascript
import * as actionTypes from './actionTypes';  
  
let nextTodoId = 0;  
  
const todo = text => ({  
    id: nextTodoId++,  
    text,  
    completed: false,  
});  
  
export const addTodo = text => ({  
    type: actionTypes.ADD_TODO,  
    todo: todo(text)  
});  
  
export const toggleTodo = id => ({  
    type: actionTypes.TOGGLE_TODO,  
    id  
});
```
$\space$
### 1.6.Reducer.js

```javascript
import * as actionTypes from'./actionTypes';  
  
const initialState = {  
    todos: []  
};  
  
export const reducer = (state=initialState, action) => {  
  
    switch(action.type) {  
  
        case actionTypes.ADD_TODO:  
            return {todos: [action.todo, ...state.todos]};  
  
        case actionTypes.TOGGLE_TODO:  
            return {todos: state.todos.map(todo => {  
                return todo.id === action.id ?   
                    {...todo, completed: !todo.completed} : todo})}  
  
        default:  
            return state;  
    }  
}  
  
export default reducer;
```
$\space$
## 2.Iteración 2-Añadir un filtro para seleccionar el tipo de TODOs
$\space$
### 2.1.Filter.jsx

```javascript
import {useSelector, useDispatch} from 'react-redux';  
  
import * as filterTypes from './filterTypes';  
import * as actions from './actions';  
import * as selectors from './selectors';  
  
const Filter = () => {  
  
    const filterType = useSelector(selectors.getFilterType);  
    const dispatch = useDispatch();  
      
    return (  
        <div>  
            <button disabled={filterType === filterTypes.ALL}   
                onClick={() => dispatch(actions.setFilter(filterTypes.ALL))}>All</button>  
            <button disabled={filterType === filterTypes.ACTIVE}  
                onClick={() => dispatch(actions.setFilter(filterTypes.ACTIVE))}>Active</button>  
            <button disabled={filterType === filterTypes.COMPLETED}  
                onClick={() => dispatch(actions.setFilter(filterTypes.COMPLETED))}>Completed</button>  
        </div>    );  
  
}  
  
export default Filter;
```
$\space$
### 2.2.Selectors.js

```javascript
import * as filterTypes from './filterTypes';  
  
export const getVisibleTodos = state => {  
  
    switch(state.filterType) {  
        case filterTypes.ALL:  
            return state.todos;  
        case filterTypes.ACTIVE:  
            return state.todos.filter(todo => !todo.completed);  
        case filterTypes.COMPLETED:  
            return state.todos.filter(todo => todo.completed);  
        default:  
            throw new Error(`Unknown filter type ${state.filterType}`);  
    }  
  
}  
  
export const getFilterType = state => state.filterType;
```
$\space$
### 2.3.Reducer.js

```javascript
import * as actionTypes from'./actionTypes';  
import * as filterTypes from './filterTypes';  
  
const initialState = {  
    todos: [],  
    filterType: filterTypes.ALL  
};  
  
export const reducer = (state=initialState, action) => {  
  
    switch(action.type) {  
  
        case actionTypes.ADD_TODO:  
            return {...state, todos: [action.todo, ...state.todos]};  
  
        case actionTypes.TOGGLE_TODO:  
            return {...state, todos: state.todos.map(todo => {  
                return todo.id === action.id ?   
                    {...todo, completed: !todo.completed} : todo})}  
  
        case actionTypes.SET_FILTER:  
            return {...state, filterType: action.filterType}  
  
        default:  
            return state;  
    }  
  
}  
  
export default reducer;
```
$\space$
## 3.Iteración 3-Implementar el reductor como una composición de reductores sencillos
Con `combineReducers` podemos combinar varios reductores individuales en uno solo para reducir la complejidad en aplicaciones grandes.
$\space$
### 3.1.Reducer.js

```javascript
import * as actionTypes from './actionTypes';
import * as filterTypes from './filterTypes';
import { combineReducers } from 'redux';

const initialState = {
    todos: [],
    filterType: filterTypes.ALL
};

const todos = (state = initialState.todos, action) => {
    switch (action.type) {
        case actionTypes.ADD_TODO:
            return [action.todo, ...state];
        case actionTypes.TOGGLE_TODO:
            return state.map(todo => {
                return todo.id === action.id ? { ...todo, completed: !todo.completed } : todo
            });
        default:
            return state;
    }
};

const filterType = (state = initialState.filterType, action) => {
    switch (action.type) {
        case actionTypes.SET_FILTER:
            return action.filterType;
        default:
            return state;
    }
};

const reducer = combineReducers({
    todos,
    filterType
});

export default reducer;
```

