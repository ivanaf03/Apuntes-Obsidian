[[Tema 1-Modelado de procesos con BPMN]]

## Piscina
Es el proceso en sí. Todos los elementos del modelo se colocan en la piscina. El nombre del proceso se coloca en su cabecera.

![[piscina bpmn.png]]
$\space$
### Ejemplo
En el ejemplo la piscina es el proceso de compra de comida online.
$\space$
## Calles 
Un actor es una abstracción de un conjunto de usuarios que interactúan con el sistema. Dos tipos de usuario que, dados los mismos recursos, ejecutan las mismas actividades, son el mismo actor.

Cada calle representa a un actor. 

![[actores bpmn.png]]
$\space$
### Ejemplo
En el ejemplo las calles son el repartidor, el restaurante, la propia aplicación y el cliente.
$\space$
## Evento de inicio
Todos los procesos tienen un evento de inicio. Indica donde empieza la ejecución de una instancia del proceso y quién la inicia. Se coloca en la calle donde el actor empieza la primera acción. Se representa con un círculo blanco.

Es un hito, no representa trabajo. 

![[inicio bpmn.png]]
$\space$
### Ejemplo
En el ejemplo el cliente inicia el proceso indicando su dirección.
$\space$
## Actividades
Una actividad es una acción que realiza un actor en un punto. Al unir actividades entre ellas se genera un flujo de trabajo. Se representan con rectángulos y el flujo con flechas.

![[actividad bpmn.png]]
$\space$
### Ejemplo
En el ejemplo las actividades son indicar la dirección, seleccionar el restaurante, seleccionar los platos, confirmar el pedido, realizar el pago, notificar el pedido, preparar el pedido y recoger el pedido (tanto cliente como repartidor).


### Condiciones
Al preparar el pedido, el flujo se divide dependiendo de una condición: si el cliente recoge el pedido o no. Para modelarlo se utiliza una puerta XOR.

![[actividad 2 bpmn.png]]

## Evento de fin
Todos los procesos tienen eventos de inicio y de fin. El evento de fin indica que el proceso finaliza cuando se llega a ese punto.

Se representa con un circulo blanco más marcado.

![[evento fin bpmn.png]]
