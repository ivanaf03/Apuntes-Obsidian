[[Tema 5-Desarrolllo basado en componentes React]]

# 1.Qué es React?
Es una librería de Javascript que sigue el paradigma del desarrollo basado en componentes. No asume el uso en tecnologías diferentes por defecto, por lo que no separa navegador, escritorio, móvil, etc. 

Sigue un enfoque minimalista, aporta lo mínimo para desarrollar un frontend. Sin embargo, contiene muchas librerías desarrolladas por la comunidad.

# 2.Componentes en React
Un componente se puede implementar con una estructura similar a una clase extendiendo de `React.Component`. Redefine los métodos que necesite, aunque el único obligatorio de implementar es `render`, que devuelve el markup del componente.

## 2.1.Estado de los componentes
Los componentes pueden tener estado. Se inicializa en el constructor. Para leerlo usamos `this.state` y para actualizarlo `this.setState`. Cada vez que se invoca a `this.setState` el componente se vuelve a renderizar.

## 2.2.Ejemplo

```javascript
import React from 'react';

class App extends React.Component {
  constructor(props) {
    super(props);
    this.state = { value: 0 };
  }

  handleIncrement() {
    this.setState({ value: this.state.value + 1 });
  }

  handleDecrement() {
    this.setState({ value: this.state.value - 1 });
  }

  handleReset() {
    this.setState({ value: 0 });
  }

  render() {
    return (
      <div>
        <p>Value: {this.state.value}</p>
        <button onClick={() => this.handleIncrement()}>Increment</button>
        <button onClick={() => this.handleDecrement()}>Decrement</button>
        <button onClick={() => this.handleReset()}>Reset</button>
      </div>
    );
  }
}

export default App;
```

## 2.3.JSX
La implementación de `render` se hace en JSX. JSX es una extensión sintáctica a JS que permite escribir expresiones en XML para describir un conjunto de elementos devueltos por un componente.

Una expresión JSX se puede incluir en cualquier lugar donde se pueda incluir una expresión.

```javascript
const element = <h1>Hello, world!</h1>;

//El entorno de ejecución transpila a:
const element = React.createElement("h1", null, "Hello, world!");
```

Dentro de una expresión JSX se puede incluir una expresión JS entre llaves.

```javascript
import React from 'react';

const App = () => {
  const name = "John";
  const age = 30;

  return (
    <div>
      <p>My name is {name}.</p>
      <p>I am {age} years old.</p>
      <p>Next year I'll be {age + 1}.</p>
    </div>
  );
}

export default App;
```

