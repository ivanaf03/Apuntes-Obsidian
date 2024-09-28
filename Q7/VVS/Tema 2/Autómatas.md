[[Tema 2-Model checkers]]

## Construcción de autómatas
La idea del model checking es construir un autómata $A_p$ que capture todas las posibles ejecuciones del programa $P$. Puede ser un autómata enorme, por lo que se debe comprobar, si aparece un nuevo estado, la existencia del mismo en una tabla hash. 

La verificación formal consiste en comprobar si una propiedad $\alpha$ se cumple. Estas propiedades se expresan en lógica lineal temporal. Para ello se debe generar un nuevo autómata, $A_{\neg\alpha}$ donde se encuentran todos los caminos donde no se cumple esta propiedad.

El objetivo es hacer la intersección de los dos autómatas. Si se obtiene un nuevo autómata sin ningún camino posible, la propiedad se cumple. Si se encuentra un camino esta propiedad no se cumple y eso es un contraejemplo.

### Autómatas de Büchi
Los model checkers trabajan con sistemas reactivos, o sea, que se están ejecutando constantemente. Se llaman trazas infinitas. La lógica lineal temporal permite describir propiedades sobre esas trazas.

Se definen en el $\omega$-lenguaje, que define conjuntos de palabras de longitud infinita. Los autómatas normales terminan en estados finales. Sin embargo, para trabajar con este lenguaje se necesitan autómatas de Büchi.

Estos son muy similares a los autómatas normales. La única diferencia es que solo aceptan secuencias infinitas. Por ejemplo, este autómata de Büchi solo acepta cadenas de longitud infinita "abababab...", es decir $(ab)^\omega$.

![[automata buchi.png]]

## Familias de model checking
Existen dos familias:
+ **Model checking explícito:** es el que usa SPIN. Se almacenan en una tabla hash todos los posibles estados. Cada estado del autómata es un estado del programa.
+ **Model checking simbólico:** los nodos del autómata engloban más de un estado del programa. Se representan con una fórmula que engloba varios estados. Se suelen representar con diagramas de decisión binarios.

### Model checking simbólico
Lo más complejo de este tipo de model checking es saber si un estado ha sido ya generado antes. Para ello debemos tener algún tipo de forma de comprobar las equivalencias.

Por ejemplo, tenemos un estado en que a = 1 y b > 0 que pasa a un estado en que a es menor que 3 y b es igual a 7. Pero puede aparecer un nuevo estado que niega que si b es mayor que 0, entonces a es distinto de 1. El estado 1 y el 3 son el mismo, se puede resolver aplicando la equivalencia de la implicación y De Morgan. Esto tiene un coste computacional. 

Para evitarlo se representan las fórmulas en BDD (Diagramas de Decisión Binarios). Sin embargo, sigue habiendo coste para construir los BDD.

## Técnicas de model checking
Dos técnicas de model checking son:
+ **Reducción de orden parcial:** cuando tenemos varios procesos entrelazados, pero no importa el orden, tenemos n! posibles caminos porque se cuentan las permutaciones. Sin embargo, si no importa el orden, se escoge una ya que las otras darían el mismo resultado.
+ **Comprobación por modelos acotada:** consiste en acotar el problema fijando un número de pasos. Esto convierte las propiedades de lógica temporal en lógica proposicional y mejora la eficiencia utilizando estos probadores. Si no se encuentra un contraejemplo se va aumentando la cota de forma indefinida.