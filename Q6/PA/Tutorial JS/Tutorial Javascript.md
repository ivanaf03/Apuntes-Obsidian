[[Programación avanzada]]

# 1.Introducción
Es un lenguaje de programación interpretado. Aunque no es su característica más destacada, permite la programación orientada a objetos. También permite programar con estilo funcional.

Se caracteriza por:
+ [>] Es sensible a mayúsculas y minúsculas.
+ [>] Es débilmente tipado.
+ [>] Es dinámico.
+ [>] Se puede usar tanto del lado del cliente como del servidor.

## 1.1.Ejemplo

```javascript
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

const isUnique = function(arr) {
    // Otro estilo
    // ...
}

let result = isUnique([1, 2, 3]);
// ...
```

# 2.Tipos de datos
Los tipos primitivos son:
+ [>] *Number:* números enteros o reales.
+ [>] *String:* cadenas de caracteres. 
+ [>] *Boolean:* true y false.
+ [>] *Null:* valor nulo.
+ [>] *Undefined:* palabra no definida.
+ [>] *Object:* conjunto de propiedades y valores.
+ [>] *Funciones:* en JS las funciones son tipos de datos.

# 3.Declaración de variables
Se pueden declarar variables con:
+ [>] *var:* no se recomienda, semántica confusa.
+ [>] *let:* variable local.
+ [>] *const:* variable constante pero, si referencia a un objeto, el contenido del objeto sí puede modificarse.

Las variables no tienen tipo, solo los valores.

## 3.1.Ejemplo

```javascript
let a = 1;
const b = 2;
a = 10; // OK
// b = 20 // ERROR: No se puede reasignar una constante

let obj1 = { prop1: 1, prop2: 'hello' };
const obj2 = { prop1: true };
obj1 = obj2; // OK: Se puede reasignar un objeto a una variable
// obj2 = obj1; // ERROR: No se puede reasignar una constante

obj1.prop1 = false; // OK: Se puede modificar una propiedad de un objeto
obj2.prop1 = false; // OK: Se puede modificar una propiedad de un objeto
```

# 4.Objetos
Los objetos tienen propiedades que pueden tener valores de cualquier tipo. Se pueden definir con literales o con clases.

```javascript
let person = {
    name: "Linda",
    age: 20,
    sex: "F"
};

console.log(`Name: ${person.name}, Age: ${person.age}, Sex: ${person.sex}`);
```

## 4.1.Clases

```javascript
class Person {
    constructor(name, age, sex) {
        this.name = name;
        this.age = age;
        this.sex = sex;
    }

    description() {
        return `Name: ${this.name}, Age: ${this.age}`;
    }
}

let person = new Person("John", 30, "M");
console.log(person.description());
```

Las clases pueden extender a otras. Se usa `super` para referenciar a la clase padre.

```javascript
class Student extends Person {
    constructor(name, age, sex, course) {
        super(name, age, sex);
        this.course = course;
    }

    description() {
        return super.description() + ` (course ${this.course})`;
    }
}

let student = new Student("John", 21, "M", 2);
console.log(student.description());
```

# 5.Funciones
## 5.1.Funciones flecha
Es otra sintaxis para las funciones, pero de una forma más compacta. No usan la palabra reservada `function`. Los parámetros van entre paréntesis, pero si solamente es un parámetro no hacen falta. Si solo tiene una sentencia se puede prescindir de las llaves y de `return`.

```javascript
function add (x, y) { 
	return x + y; 
}

const add = (x, y) => x + y;

const double = x => x * 2;

let hi = () => 'Hello!!';

const foo = (param1, param2) => { 
	let result;
	// ... 
	return result; 
};
```

## 5.2.Ejemplo: funciones como parámetros

```javascript
const loop = (array, func) => {
    const resultArray = new Array(array.length);
    for (let i = 0; i < array.length; i++) {
        resultArray[i] = func(array[i]);
    }
    return resultArray;
};

const array = [1, 2, 3, 4, 5, 6];
const arrayFinal1 = loop(array, element => (element % 2 === 0) ? element * 2 : element);
const arrayFinal2 = loop(array, element => (element % 2 === 1) ? element * 3 : element);

console.log(arrayFinal1); // [1, 4, 3, 8, 5, 12]
console.log(arrayFinal2); // [3, 2, 9, 4, 15, 6]

```

# 6.Destructuring
La sintaxis destructuring permite extraer datos de objetos o arrays.

```javascript
let person = new Person("Peter", 30, "M");

// Función que imprime el nombre y la edad de una persona
let printPerson = (per) =>
    console.log(`Name: ${per.name}, Age: ${per.age}`);

printPerson(person); // Imprime: Name: Peter, Age: 30

// Accediendo a las propiedades name y age de person directamente
let name = person.name;
let age = person.age;
console.log(`Name: ${name}, Age: ${age}`); // Imprime: Name: Peter, Age: 30

// Usando una función de flecha con desestructuración de objeto
let printPerson = ({name, age}) =>
    console.log(`Name: ${name}, Age: ${age}`);

printPerson(person); // Imprime: Name: Peter, Age: 30

// Utilizando la desestructuración de objeto para obtener name y age
let {name, age} = person;
console.log(`Name: ${name}, Age: ${age}`); // Imprime: Name: Peter, Age: 30
```

```javascript
// Definimos un array
const numbers = [1, 2, 3, 4, 5];

// Destructuración de array
const [first, second, ...rest] = numbers;

// Imprimimos las variables destructuradas
console.log(first); // Imprime: 1
console.log(second); // Imprime: 2
console.log(rest); // Imprime: [3, 4, 5]
```

# 7.Operador de propagación
Permite que un objeto iterable, como arrays o strings, sean expandidos en situaciones donde se esperan múltiples argumentos o múltiples elementos.

```javascript
const f = (x, y, z) => x + y + z;
const args1 = [0, 1, 2];
const args2 = [0, 1];

f(...args1); // Se llama a la función f con los argumentos desestructurados del array args1: 0 + 1 + 2 = 3
f(...args2, 2); // Se llama a la función f con los argumentos desestructurados del array args2 y el valor 2 como tercer argumento: 0 + 1 + 2 = 3

const continents1 = ["America", "Africa", "Oceania"];
const continents2 = ["Europe", "Asia"];

const continents3 = [...continents1, ...continents2]; // Concatenación de arrays usando spread operator: ["America", "Africa", "Oceania", "Europe", "Asia"]
const allContinents = [...continents3, "Antarctica"]; // Agregando "Antarctica" al array continents3: ["America", "Africa", "Oceania", "Europe", "Asia", "Antarctica"]
```

Este operador permite crear nuevos objetos a partir de otros haciendo una copia superficial. Si una propiedad es una string o un objeto, no copia el valor, sino la referencia.

```javascript
const defaultData = {age: 18, sex: "M"};

const person1 = {...defaultData, name: "John"};
const person2 = {...defaultData, name: "Mary", sex: "F"};

console.log(person1); // { age: 18, sex: 'M', name: 'John' }
console.log(person2); // { age: 18, sex: 'F', name: 'Mary' }
```

# 8.Ejecución
## 8.1.Ejecución síncrona
En este ejemplo, cuando se ejecute la línea 1 el thread de ejecución se queda esperando a que termine la función de sumar.

```javascript
const add = (x, y) => x + y;
result = add(1, 1); // [1]
console.log(result);
```

## 8.2.Ejecución asíncrona
En este ejemplo, cuando se ejecuta la línea 1 la función pasada como segundo parámetro no se ejecuta.

```javascript
const button = document.querySelector('#OK');
button.addEventListener('click', () => {
    alert('You clicked me!');
});
```

La ejecución de la `callback` es asíncrona. Se ejecuta cuando ocurre un determinado evento. No todas las `callback` son asíncronas.

El código de javascript se ejecuta en un solo thread. Las callback asíncronas se ejecutan cuando el thread de ejecución queda liberado y se produce el evento asociado.

Otro ejemplo son las funciones de entrada y salida, como las peticiones HTTP. Por ejemplo, una función que permita enviar una petición HTTP puede recibir dos `callback`, una que se ejecute cuando tenga éxito y otro cuando falle.

# 9.Módulos
Cada fichero es un módulo. Es necesario exportar los elementos que se quieran usar en otros módulos e importarlos en ellos. 

```javascript
export const GET = 'GET'; 
export const POST = 'POST'; 
export const PUT = 'PUT';
export const DELETE = 'DELETE’;
```

```javascript
const sendRequest = (requestType, path, headers, body, onSuccess, onErrors) => { 
	// ... 
}

export default sendRequest;
```

```javascript
import { GET, DELETE } from './requestTypes';
import send from './sendRequest';

send(GET, '/bookings/123', null, null, response => {
    // Manejar la respuesta del GET para '/bookings/123'
    // ...
}, defaultErrorHandler);

send(DELETE, '/users/456', null, null, response => {
    // Manejar la respuesta del DELETE para '/users/456'
    // ...
}, defaultErrorHandler);
```

```javascript
import * as requestTypes from './requestTypes';
import send from './sendRequest';

send(requestTypes.GET, '/bookings/123', null, null, response => {
    // Manejar la respuesta del GET para '/bookings/123'
    // ...
}, defaultErrorHandler);

send(requestTypes.DELETE, '/users/456', null, null, response => {
    // Manejar la respuesta del DELETE para '/users/456'
    // ...
}, defaultErrorHandler);

```