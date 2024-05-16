[[Tema 5-Desarrolllo basado en componentes con React]]
$\space$
## 1.Iteración 1-Texto plano de TODOs
La primera iteración consiste simplemente en crear dos etiquetas de texto plano con dos tareas.
$\space$
### 1.1.App.jsx

```javascript
import React from 'react';
import Todo from './Todo';

class App extends React.Component {
    render() {
        const todos = [
            {text: 'Learn JavaScript'},
            {text: 'Learn React'}
        ];

        return (
            <div>
                <ul>
                    <Todo todo={todos[0]} />  // los componentes pueden recibir propiedades
                    <Todo todo={todos[1]} />
                </ul>
            </div>
        );
    }
}

export default App;
```
$\space$
### 1.2.Todo.jsx

```javascript
import React from 'react';

class Todo extends React.Component {
    render() {
        const todo = this.props.todo;  // los parámetros se reciben como propiedades de this.props
        return (
            <li>{todo.text}</li>
        );
    }
}

export default Todo;
```
$\space$
## 2.Iteración 2-Hacer que `Todo` sea un componente función
Cuando un componente solo necesita redefinir `render` y no tiene estado propio puede escribirse directamente como una función que devuelva el markup del componente. Recibe `props` como parámetro, que es un objeto que contiene los parámetros del componente.
$\space$
### 2.1.Todo.jsx

```javascript
const Todo = (props) => (
  <li>{props.todo.text}</li>
);

export default Todo;
```

Otra forma de hacerlo es utilizando destructuring en lugar de pasar todo el objeto `props`.

```javascript
const Todo = ({todo}) => (  
    <li>{todo.text}</li>  
);  
  
export default Todo;
```
$\space$
## 3.Iteración 3-Crear la lista de TODOs
Cuando se renderiza una lista de un tipo de elemento, en este caso de `Todo`, se utiliza una propiedad llamada `key`. El valor de la clave es un identificador de cada uno de los ítems de la lista. Generalmente se utiliza el ID de la base de datos.

Esta estrategia no se puede emplear cuando la interfaz permita reordenar los elementos. Podría afectar a la semántica o a la renderización.

Cuando no tienen un ID natural se puede utilizar la función `map` para asignar IDs.
$\space$
### 3.1.App.jsx

```javascript
import React from 'react';
import Todos from './Todos';

class App extends React.Component {
    render() {
        const todos = [
            {id: 1, text: 'Learn JavaScript'},
            {id: 2, text: 'Learn React'}
        ];

        return (
            <div>
                <Todos todos={todos} />
            </div>
        );
    }
}

export default App;
```
$\space$
### 3.2.Todos.jsx

```javascript
import React from 'react';
import Todo from './Todo';

const Todos = ({ todos }) => (
    <ul>
        {todos.map(todo => <Todo key={todo.id} todo={todo} />)}  // expresión JSX dentro de expresión JS dentro de expresion JSX
    </ul>
);

export default Todos;
```
$\space$
## 4.Iteración 4-Añadir TODOs de forma dinámica
Podemos hacer un método `handleAddTodo` que modifique el estado de la propiedad `todos`.

```javascript
handleAddTodo(text) {
    const todos = this.state.todos;
    todos.unshift(this.todo(text));
    this.setState({ todos });
}
```

Sin embargo, es mejor mantener el estado inmutable. En lugar de cambiar el array de TODOs, es mejor crear uno nuevo.
$\space$
### 4.1.App.jsx

```javascript
import React from 'react';
import AddTodo from './AddTodo';
import Todos from './Todos';

let nextTodoId = 0;

class App extends React.Component {
    constructor(props) {
        super(props);  // Se inicializa el estado en el constructor
        this.state = { todos: [] };
    }

    todo(text) {
        return { id: nextTodoId++, text };
    }

    handleAddTodo(text) {
        this.setState({ todos: [this.todo(text), ...this.state.todos] });
    }

    render() {
        return (
            <div>
                <AddTodo onAddTodo={(text) => this.handleAddTodo(text)} />
                <Todos todos={this.state.todos} />
            </div>
        );
    }
}

export default App;
```
$\space$
### 4.2.AddTodo.jsx

```javascript
const AddTodo = ({ onAddTodo }) => {
    let input;

    return (
        <form
            onSubmit={(e) => {
                e.preventDefault();
                if (!input.value.trim()) {
                    return;
                }
                onAddTodo(input.value.trim());
                input.value = '';
            }}
        >
            <input type="text" ref={node => input = node} />  // ref permite acceder al DOM para recoger el valor del formulario
            <button type="submit">Add</button>
        </form>
    );
};

export default AddTodo;
```
$\space$
## 5.Iteración 5-Hacer que `App` sea un componente función
Para convertir los componentes en funciones podemos utilizar hooks. Son funciones que permiten acceder a características de React, como el estado de los componentes. 

Por ejemplo, `useState` permite añadir estado a un componente función. Declara una variable que mantiene el estado. Recibe el valor inicial como parámetro y devuelve un array con dos elementos, el valor actual y una función para actualizar el valor y volver a renderizar el componente.
$\space$
### 5.1.Ventajas del uso de hooks
Los hooks nos permiten:
+ [p] Reducir la dificultad de la lógica del estado entre componentes.
+ [p] Evitar redefinir métodos de `React.Component`.
+ [p] Evitar el uso de clases en JavaScript.
$\space$
### 5.2.Reglas del uso de hooks
Los hooks solo se pueden invocar desde componentes función o desde hooks a medida. Estos últimos son funciones que encapsulan varios hooks para encapsular lógica específica y reutilizable en componentes de React.

Los hooks se deben invocar siempre en el mismo orden. Para garantizarlo se debe evitar su uso en bucles, condicionales y funciones anidadas.
$\space$
### 5.3.App.jsx

```javascript
import { useState } from 'react';
import AddTodo from './AddTodo';
import Todos from './Todos';

let nextTodoId = 0;

const App = () => {
    const [todos, setTodos] = useState([]);

    const todo = text => {
        return { id: nextTodoId++, text };
    }

    const handleAddTodo = text => setTodos([todo(text), ...todos]);

    return (
        <div>
            <AddTodo onAddTodo={handleAddTodo} />
            <Todos todos={todos} />
        </div>
    );
}

export default App;
```
$\space$
## 6.Iteración 6-Cambiar el estado de un TODO
A pesar de que se haga un cambio de estado, los ítems seguirán siendo inmutables. La función `handleToggleCompleted` creará un nuevo array de TODOs con referencias a todos los TODOs excepto el que se desea cambiar, en el cual se cambiará la propiedad `completed`.
$\space$
### 6.1.App.jsx

```javascript
import {useState} from 'react';  
  
import AddTodo from './AddTodo';  
import Todos from './Todos';  
  
let nextTodoId = 0;  
  
const App = () => {  
  
    const [todos, setTodos] = useState([]);  
  
    const todo = text => {  
        return {id: nextTodoId++, text, completed: false};  
    }  
  
    const handleAddTodo = text => setTodos([todo(text), ...todos]);  
  
    const handleToggleCompleted = id => {  
  
        const newTodos = todos.map(todo => {  
            return todo.id === id ? {...todo, completed: !todo.completed} :  
                todo;  
        });  
  
        setTodos(newTodos);  
  
    }  
  
    return (  
        <div>  
            <AddTodo onAddTodo={handleAddTodo}/>  
            <Todos todos={todos} onToggleCompleted={handleToggleCompleted}/>  
        </div>   
    );  
  
}  
  
export default App;
```
$\space$
### 6.2.Todos.jsx

```javascript
import Todo from './Todo';  
  
const Todos = ({todos, onToggleCompleted}) => (  
    <ul>  
        {todos.map(todo =>   
            <Todo key={todo.id} todo={todo}  
                onToggleCompleted={onToggleCompleted}/>)  
        }  
    </ul>  
);  
  
export default Todos;
```
$\space$
### 6.3.Todo.jsx

```javascript
const Todo = ({todo, onToggleCompleted}) => (  
    <li className={todo.completed ? 'completed' : ''}  // el atributo se llama className, no class por conflictos con HTML
        onClick={() => onToggleCompleted(todo.id)}>{todo.text}</li>  
);  
  
export default Todo;
```
$\space$
## 7.Iteración 7-Filtro para seleccionar el tipo de TODOs
Se añade un nuevo componente que permite filtrar los TODOs.
$\space$
### 7.1.App.jsx

```javascript
import { useState } from 'react';
import AddTodo from './AddTodo';
import Todos from './Todos';
import Filter from './Filter';
import * as filterTypes from './filterTypes';

let nextTodoId = 0;

const App = () => {
    const [todos, setTodos] = useState([]);
    const [filterType, setFilterType] = useState(filterTypes.ALL);
    // estos dos hooks siempre se ejecutarán en el mismo orden en cada renderización de App. Internamente React mantiene un puntero a la celda actual de cada componente función. La función useState lee la celda actual y mueve el puntero a la siguiente celda.

    const todo = text => {
        return { id: nextTodoId++, text, completed: false }
    }

    const visibleTodos = () => {
        switch (filterType) {
            case filterTypes.ALL:
                return todos;
            case filterTypes.ACTIVE:
                return todos.filter(todo => !todo.completed);
            case filterTypes.COMPLETED:
                return todos.filter(todo => todo.completed);
            default:
                throw new Error(`Unknown filter type ${filterType}`);
        }
    }

    const handleAddTodo = text => setTodos([todo(text), ...todos]);

    const handleToggleCompleted = id => {
        const newTodos = todos.map(todo => {
            return todo.id === id ? { ...todo, completed: !todo.completed } : todo;
        });
        setTodos(newTodos);
    }

    const handleFilterClick = filterType => setFilterType(filterType);

    return (
        <div>
            <AddTodo onAddTodo={handleAddTodo} />
            <Todos todos={visibleTodos()} onToggleCompleted={handleToggleCompleted} />
            <Filter filterType={filterType} onFilterClick={handleFilterClick} />
        </div>
    );
}

export default App;
```

