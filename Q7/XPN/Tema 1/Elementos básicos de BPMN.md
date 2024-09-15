[[Tema 1-Modelado de procesos con BPMN]]

## Piscina
Es el lugar donde se colocan todos los elementos del modelo. El nombre del proceso se pone en la cabecera de la piscina.

![[piscina bpmn.png]]

## Calles y actores
Los actores son abstracciones de un conjunto de usuarios que interactúan con el sistema. Dos actores son el mismo actor si dados los mismos recursos pueden ejecutar las mismas actividades.

Cada calle de la piscina representa un actor. En el ejemplo son actores el cliente, el sistema, el restaurante y el repartidor.

![[actores bpmn.png]]

## Evento de inicio
Todos los procesos tienen un evento que marca el inicio. Señala donde empieza la ejecución de una instancia del proceso. El evento de inicio abstracto es un hito que se coloca en la calle donde empieza la primera acción.

Se representa con un circulo blanco.

![[inicio bpmn.png]]




Evento de inicio: no representa trabajo, puede ir en cualquier sitio. 

Actividad: acción que realiza un actor. indicar dirección, seleccionar restaurante, marcar platos, registrar pedido, completar pago, notificar pedido, notificar a repartidor, preparar pedido, recoger pedido, entregar pedido.

Condición recoger (repartidor) -> entregar o recoger directamente

Función split: separar un camino en varios

Función merge: unir varios caminos en uno

Todo proceso tiene evento de inicio y de fin. 

Principalmente se representa el flujo de trabajo de como ocurren las cosas. En el ejemplo de la bicicleta siempre se seguiría la misma orden.
