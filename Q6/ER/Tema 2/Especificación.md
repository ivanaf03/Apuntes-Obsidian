[[Tema 2-La máquina y el mundo]]

## ¿Cómo se hace la especificación?
Para demostrar que los requisitos son satisfacibles por un software hacemos una especificación de este. 

$$P, M \rightarrow S$$

Esta relación indica que todos los artefactos relacionados con nuestro sistema tienen una función en él.

 Esto no es infalible. Por ejemplo, en un sistema de gestión de tráfico:
+ E: los coches paran cuando el semáforo está en rojo.

No es verdad porque algunos conductores se saltan los semáforos.

## Designaciones
Una designación es un `mapping` entre los términos de los requisitos y una especificación formal. Por ejemplo, en la entrada de un parque:
+ El cliente dice que quiere una entrada.
+ El sistema reconoce que entrar es girar el torno de la entrada N grados.
+ La especificación es el puente intermedio entre lo que dice el cliente y lo que hace el sistema.

## Ejemplo
Si el requisito es que un paciente tiene una desviación en el pulso, el sistema emite un sonido. La especificación es que emita un sonido. Esto es incompleto, tenemos que tener en cuenta el entorno o dominio. Si no hay nadie escuchando, esto no sería correcto.