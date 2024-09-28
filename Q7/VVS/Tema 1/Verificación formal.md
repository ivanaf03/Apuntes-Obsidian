[[Tema 1-Introducción a VVS]]

## Objetivos de la verificación formal
El objetivo es probar la corrección de un sistema, tanto software como hardware. Para ello se utilizan métodos formales.

### Métodos formales
Se dividen en:
+ **Especificación formal:** consiste en enunciar las propiedades de un sistema mediante un lenguaje formal. Son fórmulas lógicas. Indica qué debe hacer el sistema, pero no cómo.
+ **Verificación formal:** consiste en demostrar que el programa cumple la especificación. Se usan fundamentos matemáticos para modelar los sistemas.

## Especificación formal
El objetivo de la especificación formal es escribir una fórmula que describa la solución del problema. La fórmula debe ser siempre correcta, es decir, que cumpla una condición necesaria y suficiente. Por ejemplo:

$$
x \mod a = 0 \land y \mod a = 0 \land \neg \exists z > a \, (x \mod z = 0 \land y \mod z = 0)
$$

Si un programa garantiza una condición necesaria, pero no suficiente, solo garantiza que si el programa quiere llegar a su objetivo, debe cumplir esa propiedad obligatoriamente. Por ejemplo:

$$
x = k \cdot y \implies a = y
$$

### Casos de prueba
Los casos de prueba son condiciones necesarias que prueban un caso concreto. Por ejemplo:

$$
x = 60 \land y = 45 \implies a = 15
$$

## Cobertura de la verificación
Hay varias capas a la hora de hablar de verificación dependiendo de lo fuerte que sea la cobertura. La forma más básica son los casos de prueba.

### Generadores de tests
Una forma de generar muchos casos de prueba es probar una cantidad enorme de valores. Se hace con herramientas generadoras de tests, pero no dejan de ser pruebas de condiciones necesarias.

### Model checking
Es una forma de comprobar todas las posibles ejecuciones de un programa. Garantiza que se cumplan todas las condiciones necesarias y suficientes, aunque solamente funciona en dominios finitos o dominios infinito representables como conjuntos finitos.

### Prueba de teoremas
Aplica a dominios infinitos también. Si se consigue una demostración matemática de la corrección de un programa eso prueba en cualquier dominio que se cumplen las condiciones necesarias y suficientes.

## Testing vs. verificación formal

|             | Prueba y error                                      | Verificación formal                                |
| ----------- | --------------------------------------------------- | -------------------------------------------------- |
| Confianza   | Nunca se consigue cubrir el 100% de los casos.      | Usa métodos matemáticos, por lo que es muy fiable. |
| Punto clave | Buen diseño de casos de prueba.                     | Realizar una buena especificación.                 |
| Entrada     | Programa.                                           | Algoritmo.                                         |
| Eficiencia  | Se mide en tiempo de ejecución y memoria consumida. | Se mide la complejidad.                            |

### Problema de la verificación formal
La situación ideal para la verificación formal es que dado el programa y las fórmulas que se quieren probar se consiga, o bien, si son correctas un caso de prueba y, sino, un contraejemplo. Desafortunadamente, a veces no se consigue responder en tiempo finito a uno de los dos casos. Un ejemplo es el problema de la para de Turing.

## Model checking vs. prueba de teoremas
La prueba de teoremas se basa en utilizar inferencias lógicas. No es automática, debe haber alguien como mínimo probando estrategias o controlándola. Puede usarse en dominios infinitos aunque a veces no se sepa si la proposición es verdadera o falsa. Se usa para algoritmos que se crea que están correctos, ya que no sirve para generar contraejemplos.

El model checking es una exploración exhaustiva de todos los estados de un modelo. Solo trabaja en dominios finitos o dominios infinitos con representación finita. Es completamente automático. Si una propiedad se cumple, encuentra un contraejemplo para ella. Se usa en sistemas reactivos, es decir, que se ejecutan continuamente, mediante la aplicación de lógica temporal.