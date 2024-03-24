[[Tema 5-Desarrolllo basado en componentes React]]

# 1.IT-1: versión inicial de un TODO

```javascript
//App.jsx
import Todo from './Todo';

class App extends React.Component {
  render() {
    const todos = [
      { text: 'Learn JavaScript' },
      { text: 'Learn React' }
    ];

    return (
      <div>
        <ul>
          <Todo todo={todos[0]} />
          <Todo todo={todos[1]} />
        </ul>
      </div>
    );
  }
}

export default App;
```

```javascript
//Todo.jsx
import React from 'react';

class Todo extends React.Component {
  render() {
    const todo = this.props.todo;
    return (
      <li>{todo.text}</li>
    );
  }
}

export default Todo;
```

# 2.IT-2: TODO como componente función
Cuando un componente no tiene estado y solo necesita redefinir `render` se puede escribir simplemente una función que devuelve el markup del componente. Recibe el objeto `props` como parámetro, que contiene los parámetros del componente.

```javascript
//Todo.jsx
const Todo = ({ todo }) => (
  <li>{todo.text}</li>
);

export default Todo;
```

# 3.IT-3: primera versión de componente TODO

```javascript
//App.jsx
import Todos from './Todos';

class App extends React.Component {
  render() {
    const todos = [
      {id: 1, text: 'Learn JavaScript'},
      {id: 2, text: 'Learn React'}
    ];
    return (
      <div>
        <Todos todos={todos}/>
      </div>
    );
  }
}
```

```javascript
//Todos.jsx
import Todo from './Todo';

const Todos = ({todos}) => (
  <ul>
    {todos.map(todo => <Todo key={todo.id} todo={todo}/>)}
  </ul>
);

export default Todos;
```

Al renderizar una lista de un tipo de elemento debemos emplear la propiedad `key`. Es un identificador único entre las partes de la lista. Se suele usar el ID de BBDD como valor de `key`. Cuando no se puede hacer esto de forma natural podemos usar la función `map`.

```javascript
{todos.map((todo, index) => <Todo key={index} todo={todo}/>)}
```

# 4.IT-4: añadir TODOs dinámicamente

```javascript
//App.jsx
import React from 'react';
import AddTodo from './AddTodo';
import Todos from './Todos';
let nextTodoId = 0;

class App extends React.Component {
  constructor(props) {
    super(props);
    this.state = {todos: []};
  }

  todo(text) {
    return {id: nextTodoId++, text};
  }

	handleAddTodo(text) {
	  this.setState({todos: [this.todo(text), ...this.state.todos]});
	}
	
	render() {
	  return (
	    <div>
	      <AddTodo
	        onAddTodo={(text) => this.handleAddTodo(text)}
	      />
	      <Todos todos={this.state.todos}/>
	    </div>
	  );
	}
}

export default App;
```

Aunque el método `handleAddTodo` se podría haber implementado modificando directamente el valor de la propiedad `this.state` es preferible tratar cada propiedad como objeto inmutable. Esto se hace con el operador de propagación en el ejemplo.

```javascript
//MUTABLE
handleAddTodo(text) {
  const todos = this.state.todos;
  todos.unshift(this.todo(text));
  this.setState({todos});
}

//INMUTABLE
handleAddTodo(text) {
  const todos = this.state.todos;
  this.setState({todos: [this.todo(text)].concat(todos)});
}
```

```javascript
//AddTodo.jsx
const AddTodo = ({onAddTodo}) => {
  let input;

  return (
    <form onSubmit={(e) => {
      e.preventDefault();
      if (!input.value.trim()) {
        return;
      }
      onAddTodo(input.value.trim());
      input.value = '';
    }}>
      <input type="text" ref={node => input = node}/>
      <button type="submit">Add</button>
    </form>
  );
}

export default AddTodo;
```

# 5.IT-5: reescribir App como componente función
Los Hooks son funciones especiales de React que permiten implementar la mayor parte de los componentes como funciones. Solucionan los siguientes problemas:
+ [>] Dificultad para reusar lógica con estado entre componentes.
+ [>] Código difícil de entender en componentes complejos de `React.Component`.
+ [>] Características confusas de las clases de Javascript. 

$\space$
Permiten acceder a características de React, como el estado del componente desde componentes función. Existen Hooks predefinidos, pero podemos implementar nuestros propios Hooks.

```javascript
import { useState } from 'react';

const App = () => {
  const [todos, setTodos] = useState([]);
  
  const todo = text => {
    return { id: nextTodoId++, text };
  };
  
  const handleAddTodo = text => setTodos([todo(text), ...todos]);
  
  return (
    <div>
      <AddTodo onAddTodo={handleAddTodo}/>
      <Todos todos={todos}/>
    </div>
  );
}

export default App;
```

`useState` es un hook predefinido que permite añadir estado a un componente función. Se declara una variable de estado. `useState` siempre devolverá el valor de esa variable entre distintas invocaciones del componente función.

Recibe el valor inicial como parámetro y devuelve un array con dos elementos:
+ [>] Valor actual.
+ [>] Función que actualiza el valor. 

$\space$
La primera renderización de App `useState` devuelve una lista vacía para `todos`. Cada vez que se invoca a `setTodos` el componente se vuelve a renderizar y `todos` devuelve el valor actual.

Los Hooks siguen 2 reglas:
+ [>] *Regla 1:* solo se pueden invocar desde componentes función y Hooks a medida.
+ [>] *Regla 2:* un componente función o Hook a medida puede invocar múltiples Hooks. Para que se asocie el estado de los Hooks correctamente debemos hacerlo siempre en el mismo orden, evitando bucles, sentencias condicionales y funciones anidadas. 

# 6.IT-6: cambiar el estado de un TODO

```javascript
//App.jsx
const todo = text => {
  return {id: nextTodoId++, text, completed: false};
}

const handleToggleCompleted = id => {
  const newTodos = todos.map(todo => {
    return todo.id === id ? {...todo, completed: !todo.completed} : todo;
  });
  setTodos(newTodos);
}

return (
  <div>
    <AddTodo onAddTodo={handleAddTodo}/>
    <Todos todos={todos} onToggleCompleted={handleToggleCompleted}/>
  </div>
);
```

`todos` se trata como un inmutable. La función `handleToggleCompleted` crea un nuevo vector de TODOs. Contiene referencias a todos los TODOs excepto al que se desea cambiar. Para este se crea uno nuevo con todos las propiedades y valores idénticos al anterior excepto la propiedad `completed`.

```javascript
//Todos.jsx
const Todos = ({todos, onToggleCompleted}) => (
  <ul>
    {todos.map(todo =>
      <Todo key={todo.id} todo={todo} onToggleCompleted={onToggleCompleted}/>
    )}
  </ul>
);
```

```javascript
//Todo.jsx
const Todo = ({todo, onToggleCompleted}) => (
  <li className={todo.completed ? 'completed' : ''} onClick={() => onToggleCompleted(todo.id)}>
    {todo.text}
  </li>
);
```

# 7.IT-7: filtro para mostrar todos los TODO, solo los activos o solo los completados

```javascript
const App = () => {
  const [todos, setTodos] = useState([]);
  const [filterType, setFilterType] = useState(filterTypes.ALL);

  const handleAddTodo = text => setTodos([todo(text), ...todos]);
  const handleFilterClick = filterType => setFilterType(filterType);

...

  return (
    <div>
      {/* Aquí va el resto del código del componente */}
    </div>
  );
}
```

