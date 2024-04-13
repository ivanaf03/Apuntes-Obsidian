[[Programación avanzada]]

## 1.Qué es JavaScript?
JavaScript es un lenguaje de programación interpretado. Permite programar orientado a objetos y con estilo funcional.

### 1.1.Características
JavaScript tiene ciertas peculiaridades:
+ Es sensible a mayúsculas y minúsculas.
+ Tiene tipado débil, por lo que no se declaran tipos. El tipo esta asociado a el valor que se le da a la variable.
+ Es dinámico, es decir, permite añadir propiedades a los objetos en tiempo de ejecución.
+ Se puede usar tanto del lado cliente como del lado servidor.

## 2.Tipos de datos
Existen 3 tipos de datos en JavaScript.

### 2.1.Tipos primitivos
Los tipos primitivos son:
+ **Number:** números enteros o reales.
+ **String:** cadenas de caracteres.
+ **Boolean:** true o false.
+ **Null:** ausencia intencionada de valor; representa la nada.
+ **Undefined:** ausencia de valor.

### 2.2.Objetos
Los objetos en JavaScript son conjuntos de propiedades con un valor asociado. Los arrays también son objetos en este lenguaje.

```javascript
let persona = {
    nombre: "Juan",
    edad: 30,
    ciudad: "Madrid"
};

console.log(persona.nombre); // Output: Juan
console.log(persona.edad); // Output: 30
console.log(persona.ciudad); // Output: Madrid
```

```javascript
let frutas = ["manzana", "banana", "naranja"];

console.log(frutas[0]); // Output: manzana
console.log(frutas[1]); // Output: banana
console.log(frutas[2]); // Output: naranja
```

#### 2.2.1.Clases
Son un tipo especial de objetos. Son muy similares a las clases en Java. Están formadas por el constructor y por métodos. Permiten herencia y el uso de `super`.

```javascript
class Animal {

  constructor(nombre) {
    this.nombre = nombre;
  }

  saludar() {
    console.log(`Hola, soy ${this.nombre}.`);
  }
}

class Perro extends Animal {

  constructor(nombre, raza) {
    super(nombre);
    this.raza = raza;
  }

  presentarse() {
    console.log(`Soy un perro de raza ${this.raza}.`);
  }
}

let miPerro = new Perro("Bobby", "Labrador");
miPerro.saludar(); // Output: Hola, soy Bobby.
miPerro.presentarse(); // Output: Soy un perro de raza Labrador.
```

### 2.3.Funciones
Las funciones también son tipos de datos en JavaScript. Existen varias formas de definir funciones.

```javascript
//Primera forma de declaración de funciones
function isUnique(arr) {
    for (let i = 0; i < arr.length; i++) {
        let j = i + 1;
        while (j < arr.length) {
            if (arr[i] === arr[j]) {
                return false;
            }
            j++;
        }
    }
    return true;
}

let result = isUnique([1, 2, 3]);
console.log(result);
```

```javascript
//Segunda forma de declaración de funciones
const isUnique = function(arr) {
    for (let i = 0; i < arr.length; i++) {
        let j = i + 1;
        while (j < arr.length) {
            if (arr[i] === arr[j]) {
                return false;
            }
            j++;
        }
    }
    return true;
}

let result = isUnique([1, 2, 3]);
console.log(result);
```

#### 2.3.1.Funciones flecha
Las funciones flecha son una alternativa a las funciones normales. Permiten una sintaxis mucho más compacta. No utilizan la palabra `function`, en su lugar usan una flecha `=>`.

```javascript
const suma = (a, b) => {
  return a + b;
};
```

Si solamente tienen un parámetro no necesitan paréntesis. Además si solo es una sentencia no necesita ni siquiera `return`.

```javascript
const cuadrado = x => x * x;

console.log(cuadrado(5)); // Output: 25
```

#### 2.3.2.Funciones como parámetros
Se pueden pasar funciones como parámetros a otras funciones.

```javascript
const loop = (array, func) => {
    const resultArray = new Array(array.length);
    for (let i = 0; i < array.length; i++) {
        resultArray[i] = func(array[i]);
    }
    return resultArray;
}

const array = [1, 2, 3, 4, 5, 6];
const arrayFinal1 = loop(array,
    element => (element % 2 === 0) ? element * 2 : element
);
const arrayFinal2 = loop(array,
    element => (element % 2 === 1) ? element * 3 : element
);
console.log(arrayFinal1); // [1, 4, 3, 8, 5, 12]
console.log(arrayFinal2); // [3, 2, 9, 4, 15, 6]
```

## 3.Tipos de variables
Existen tres tipos de variables en JavaScript:
+ **var:** variable que se puede redefinir dentro de la misma función o ámbito. No se recomienda su uso.
+ **let:** variable local.
+ **const:** constante local. Si referencia a un objeto, el contenido del objeto puede modificarse.

### 3.1.Ejemplo 

```javascript
let a = 1;
const b = 2;
a = 10; // OK
b = 20 // ERROR: No se puede reasignar una constante

let obj1 = { prop1: 1, prop2: 'hello' };
const obj2 = { prop1: true };
obj1 = obj2; // OK: Se puede reasignar un objeto a una variable
obj2 = obj1; // ERROR: No se puede reasignar una constante

obj1.prop1 = false; // OK: Se puede modificar una propiedad de un objeto
obj2.prop1 = false; // OK: Se puede modificar una propiedad de un objeto
```

## 4.Destructuring
El destructuring es una característica de JavaScript que permite extraer valores de objetos o arrays y asignarlos a variables de una forma sencilla.

```javascript
const person = { name: 'John', age: 30 };
const { name, age } = person;
console.log(name); // 'John'
console.log(age); // 30
```

## 5.Operador de propagación
El operador de propagación `...` permite expandir expresiones en lugares donde se esperan múltiples elementos o argumentos. 

```javascript
const f = (x, y, z) => x + y + z;
const args1 = [0, 1, 2];
const args2 = [0, 1];

f(...args1);
f(...args2, 2);
```

```javascript
const continents1 = ["America", "Africa", "Oceania"];
const continents2 = ["Europe", "Asia"];
const continents3 = [...continents1, ...continents2];
const allContinents = [...continents3, "Antarctica"];
```

### 5.1.Copia superficial
El operador de propagación también se puede usar para crear nuevos objetos a partir de otros. Esto se llama copia superficial. Si una propiedad es una string o un objeto no se copia el valor, solo la referencia a este.

```javascript
const defaultData = {age: 18, sex: "M"};
const person1 = {...defaultData, name: "John"};
const person2 = {...defaultData, name: "Mary", sex: "F"};

console.log(person1); // { age: 18, sex: 'M', name: 'John' }
console.log(person2); // { age: 18, sex: 'F', name: 'Mary' }
```

## 6.Ejecución 
JavaScript permite dos tipos de ejecución:
+ Síncrona
+ Asíncrona

### 6.1.Ejecución síncrona
Las operaciones se ejecutan de forma secuencial según están escritas en el código. Si una operación tarda mucho en completarse, el programa se queda en espera hasta que termina esa operación.

```javascript
const add = (x, y) => x + y;
result = add(1, 1);
console.log(result);
```

### 6.2.Ejecución asíncrona
Las operaciones asíncronas permiten que otras operaciones se sigan ejecutando mientras ellas no terminan. Se suelen utilizar en tareas largas, como lecturas de archivos, accesos a BBDD o esperas de una respuesta de red. Se manejan con `callbacks`, `promises` o `async/await`.

Como el código JavaScript se ejecuta en un solo thread las `callbacks` se ejecutan cuando el thread queda libre y se produce el evento.

```javascript
const button = document.querySelector('#OK');
button.addEventListener('click', () => {
    alert('You clicked me!');
});
```

La función pasada como segundo parámetro a `addEventListener` es un `callback`. No se ejecuta, sino que se queda esperando a que alguien pulse el botón.

## 7.Módulos
Los ficheros en JavaScript se consideran módulos independientes. Para acceder a un elemento de un módulo desde otro debemos exportar ese elemento e importarlo desde nuestro módulo. 

Los `import` y `export` no pueden estar dentro de funciones o clases. Deben ser accesibles desde el nivel principal.

### 7.1.Ejemplo

```javascript
// utils.js
export function greet(name) {
    return `Hello, ${name}!`;
}
```

```javascript
// main.js
import { greet } from './utils.js';

console.log(greet('John')); // Salida: "Hello, John!"
```