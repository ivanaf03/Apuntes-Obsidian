[[Tema 2-Automatización de procesos]]

## Puerta XOR
Las ramas de salida se ejecutan en un orden determinado, ya que puede haber más de una rama que cumpla las condiciones, pero no tendría sentido. Esto se llama transition ordering. Una vez evalúa una rama como verdadera, no continúa evaluando las otras.

Las condiciones se configuran en las ramas mediante una expresión en Groovy. Esto también se puede hacer en la tabla de decisiones. Los datos que se evalúan en estas condiciones son variables de proceso previamente obtenidas o calculadas.

## Puerta AND
Puede tener dos o más ramas de salida. Cuando llega al flujo, las activa todas. No tiene asociados datos locales, ni operaciones y nada relacionado con la ejecución.

## Puerta OR
Funciona de forma similar a la XOR, pero evalúa todas las ramas y activa todas aquellas que cumplan la condición. En caso de ser una puerta de cierre, se activa cuando lleguen a ella todos los caminos activos.