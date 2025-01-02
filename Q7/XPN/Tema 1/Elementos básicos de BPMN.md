[[Tema 1-Modelado de procesos con BPMN]]

## Elementos básicos
Los elementos de BPMN son:
+ **Piscina:** es el propio proceso. Todos los elementos se colocan dentro de ella. Se identifica con un nombre único que se pone en la cabecera. Por ejemplo, en el caso anterior es  "Proceso de compra de comida online".

![[piscina_bpmn.png]]

+ **Calles:** son los actores del proceso. Un actor es una abstracción de un usuario o conjunto de usuarios que interactúan con el sistema. Pueden ser un conjunto de usuarios, ya que si dados los mismos recursos ejecutan las mismas actividades, entonces son el mismo actor. En el caso anterior los actores son el cliente, la propia aplicación, el restaurante y el repartidor.

![[calles_bpmn.png]]

+ **Evento de inicio:** es el lugar donde comienza en proceso e indica donde empieza la ejecución de cada instancia del proceso. Es obligatorio. Se suele colocar en la calle donde va a realizarse la primera acción, aunque no es obligatorio. Los eventos son hitos, por lo que no representa trabajo. En el caso anterior el cliente comienza el proceso indicando la dirección.

![[Imágenes/inicio_abstracto_bpmn.png]]

+ **Actividad:** es una acción que realiza un actor en un punto concreto. Se unen entre ellas para generar el workflow. En el caso anterior eran actividades indicar la dirección, seleccionar el restaurante, seleccionar los platos, confirmar el pedido, realizar el pago, notificar el pedido, preparar el pedido, recoger pedido siendo cliente, desplazarse hacia al restaurante, recoger pedido siendo repartidor y entregar el pedido.

![[actividad_bpmn.png]]

+ **Puerta XOR:** permite representar una condición que divide el flujo en varios caminos. Sirve tanto para dividir caminos, lo que se conoce como split, como para juntarlos, lo que se conoce como merge. En el caso anterior se utiliza para modelar si es un reparto a domicilio o no.

![[xor_bpmn.png]]

+ **Evento de fin:** es el lugar donde termina el proceso. Puede haber más de un evento de fin.

![[evento_fin_bpmn.png]]

