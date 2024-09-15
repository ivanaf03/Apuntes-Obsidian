[[Tema 1-Introducción a VVS]]

## Verificación formal
El objetivo de la verificación formal es probar que un software o que un circuito hardware es correcto. Se llama verificación formal porque usa los dos métodos formales:
+ **Especificación formal:** son fórmulas que indican lo qué debe hacer el programa, sin indicar cómo debe hacerlo.
+ **Verificación formal:** son pruebas que indican que el sistema satisface la especificación.

### Ejemplo: algoritmos de ordenación
Para realizar una especificación formal de un programa que use un algoritmo de ordenación, no importa que algoritmo seleccionar, ya que todos ordenarán el vector.

Sin embargo, si la especificación indica que debemos usar un algoritmo concreto, por ejemplo quicksort, la verificación formal debe descartar todos los demás.

## Especificación formal
El objetivo de la verificación formal es escribir una fórmula que defina correctamente el problema. Por ejemplo, el problema es siempre correcto si y solo si:

$$a = \gcd(x, y) \iff \left( x \mod a = 0 \wedge y \mod a = 0 \wedge \neg \exists z > a \left( x \mod z = 0 \wedge y \mod z = 0 \right) \right)$$

Para hacer pruebas, basta con cumplir una condición necesaria, no hace falta que sea suficiente. Si una de ellas falla, el programa está mal. Se usan para encontrar errores. Por ejemplo, en el caso anterior una posible prueba sería:

$$x = k \cdot y \implies a = y$$

## Tipos de verificación
Existen varios tipos de verificación que engloban unos a otros.

### Para testing en ingeniería de software
Los más básicos son los casos de prueba, por ejemplo, comprobar si para x=60 e y=45, a vale 15.

Los generadores de tests automatizan esto probando muchos casos. Por ejemplo, realizar un bucle de valores de k para comprobar la condición necesaria mencionada en el apartado anterior.

### Para verificación formal
El model checking prueba todos los posibles casos que satisfacen las condiciones necesarias y suficientes, pero solo trabaja en dominios finitos. Por ejemplo, no serviría para probar en máximo común divisor.

Por último, la prueba de teoremas engloba todos los casos de pruebas y también funciona en dominios infinitos.

## Verificación formal contra prueba y error

|            | Prueba y error                                      | Verificación formal                                |
| ---------- | --------------------------------------------------- | -------------------------------------------------- |
| Confianza  | Nunca se consigue cubrir el 100% de los casos.      | Usa métodos matemáticos, por lo que es muy fiable. |
| Uso        | Casos de prueba.                                    | Realizar una buena especificación.                 |
| Entorno    | Programa.                                           | Algoritmo.                                         |
| Eficiencia | Se mide en tiempo de ejecución y memoria consumida. | Se mide la complejidad.                            |

## Situación ideal
La situación ideal de la verificación formal es que, dados el programa y las fórmulas consigamos, si está bien, un caso de prueba y, si no, un contraejemplo. La realidad es que a veces no se puede responder en tiempo finito a uno de estos casos. Por ejemplo, en el problema de la parada de Turing.

## Model checking contra prueba de teoremas
La prueba de teoremas se basa en utilizar inferencias lógicas. No es automática, debe haber alguien como mínimo probando estrategias o controlándola. Puede usarse en dominios infinitos aunque a veces no se sepa si la proposición es verdadera o falsa. Se usa para algoritmos que se crea que están correctos, ya que no sirve para generar contraejemplos.

El model checking es una exploración exhaustiva de todos los estados de un modelo. Solo trabajo en dominios finitos o dominios infinitos con representación finita. Es completamente automático. Si una propiedad se cumple, encuentra un contraejemplo para ella. Se usa en sistemas reactivos, es decir, que se ejecutan continuamente, mediante la aplicación de lógica temporal.

El model checking es la exploración exhaustiva de todos los estados de un modelo. Necesita dominio finito. Es completamente automático. Cuando una propiedad no se cumple, encuentra un contraejemplo. Se usa en sistemas que se están ejecutando continuamente mediante la aplicación de la lógica temporal. 