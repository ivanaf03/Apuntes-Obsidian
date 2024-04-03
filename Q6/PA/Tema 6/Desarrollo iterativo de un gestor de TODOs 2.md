[[Tema 6-Gestión de estado con Redux]]

## 1.Iteración 1 (crear una versión que permita añadir TODOs y cambiar su estado)
```javascript
//App.jsx
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

```javascript
//AppTodo.jsx
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

```javascript
//Todos.jsx
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

```javascript
//ActionTypes.jsx
export const ADD_TODO = 'ADD_TODO';
export const TOGGLE_TODO = 'TOGGLE_TODO';
```

```javascript
//Actions.js
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

```javascript
//Reducer.js
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

## 2.Iteración 2 (añadir un filtro que seleccione todos los TODOs, solo los activos y solo los completados)

```javascript
//Filter.jsx
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
        </div>
    );

}

export default Filter;
```

```javascript
//Selector.js
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

```javascript
//Reducer.js
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

Cuando se hace click en un TODO se renderiza solo el componente TODOs. Cuando se selecciona un filtro se renderizan los TODOs y los filtros.

## 3.Iteración 3 (implementar el reductor como una composición de reductores más sencillos)

```javascript
//Reducer.js
import {combineReducers} from 'redux';

import * as actionTypes from'./actionTypes';
import * as filterTypes from './filterTypes';

const initialState = {
    todos: [],
    filterType: filterTypes.ALL
};

const todos = (state=initialState.todos, action) => {

    switch(action.type) {

        case actionTypes.ADD_TODO:
            return [action.todo, ...state];

        case actionTypes.TOGGLE_TODO:
            return state.map(todo => {
                return todo.id === action.id ? 
                    {...todo, completed: !todo.completed} : todo});

        default:
            return state;
    }

};

const filterType = (state=initialState.filterType, action) => {

    switch(action.type) {

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

