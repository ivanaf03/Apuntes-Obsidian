[[Tema 5-Desarrolllo basado en componentes con React]]

## 1.Qué es React?
React es una librería de JavaScript que sigue el paradigma de desarrollo basado en componentes. Se adapta a diferentes entornos y tecnologías como móvil, navegador, escritorio, etc. 

Sigue un enfoque minimalista, solo aporta lo mínimo necesario para el desarrollo del frontend. Sin embargo, se complementa con la gran variedad de librerías desarrolladas por la comunidad.

### 1.1.Componentes en React
Un componente se puede implementar como una clase que hereda de `React.Component`. Puede redefinir todos los métodos que necesite, pero el único obligatorio es `render`, que devuelve el markup del componente.

#### 1.1.1.Estado de los componentes
El estado de los componentes se inicializa en el constructor y es una propiedad del objeto. Se puede leer con `this.state` y se puede actualizar con `this.setState`. Este método recibe un objeto con las propiedades que se desean modificar. Cuando se llama a este método el componente se vuelve a renderizar.

#### 1.1.2.Ejemplo: pa-counter

```javascript
// App.jsx
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
                {this.state.value + ' '}
                <button onClick={() => this.handleIncrement()}>+</button>
                {' '}
                <button onClick={() => this.handleDecrement()}>-</button>
                {' '}
                <button onClick={() => this.handleReset()}>Reset</button>
            </div>
        );
    }

}

export default App;
```

## 2.JSX
La implementación de `render` se hace en JSX. Es una extensión de la sintaxis de JavaScript que permite escribir código HTML de manera similar a la sintaxis de XML.

Los ficheros que utilizan expresiones JSX deben tener la extensión `.jsx`.

### 2.1.Expresiones JSX
Una expresión JSX funciona igual que una expresión JavaScript.

```javascript
const element=<h1>Hola mundo!</h1>

//Equivale a 
const elemento=React.createElement("h1", null, "Hola mundo!");
```

Permiten incluir expresiones JavaScript dentro de ellas entre llaves.

```javascript
<button onClick={() => this.handleReset()}>Reset</button>
```
