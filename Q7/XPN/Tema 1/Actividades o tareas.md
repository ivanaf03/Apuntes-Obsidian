[[Tema 1-Modelado de procesos con BPMN]]

## Qué son las actividades?
> [!abstract] Definición de actividad
> Las actividades o tareas son las encargas de modelar el trabajo que realiza un actor en un punto del proceso.

 Se colocan en la calle que representa al actor que realiza dicho trabajo. Deben cumplir el principio de responsabilidad única.

## Tipos de actividades
En las primeras versiones del modelado, se pueden utilizar actividades abstractas. Estas no tienen un tipo concreto asociado y no se pueden implementar en los motores de automatización. No obstante, existen otros tipos de actividades con semántica.

![[tareas_tipos_bpmn.png]]

### Tareas de tipo usuario
Las tareas de tipo usuario modelan las acciones en las que el usuario interactúa directamente con el sistema y genera alguna entrada. La interacción se produce mediante algún tipo de interfaz. 

### Tareas de tipo manual
Las tareas de tipo manual se definen en el análisis, pero no se implementan. Modelan trabajo que realiza el usuario sin interaccionar con la aplicación.

### Tareas de tipo servicio
Las tareas de tipo servicio modelan las acciones automáticas que realiza el sistema sin que el usuario interactúe con él. Por ejemplo, llamadas a servicios, cálculos intermedios de los procesos, ejecuciones de sentencias SQL...

### Tareas de tipo script
Las tareas de tipo script son muy similares a las tipo servicio, pero las ejecuta el propio motor de automatización. 

### Tareas de reglas de negocio
Las tareas de reglas de negocio son triggers que se suelen representar explícitamente en sistemas externos. Por ejemplo, una regla de negocio puede ser reponer el stock cuando cae por debajo del 20%. Permiten juntar en un solo lugar todo el comportamiento de los esquemas de información sin tocar código.

## Ejemplo: tipos de actividades en el pedido de comida online

![[ejemplo_tareas_bpmn.png]]

## Subprocesos
> [!abstract] Definición de subproceso
> Es un proceso que tiene suficiente significado como para poder ejecutarse de forma independiente, lo que le permite ser reciclado e invocado por más de un proceso a la vez.

Son muy útiles para evitar repetir implementaciones.  Por ejemplo, el proceso de emitir factura que podría haber después de efectuar el pago podría utilizarse en otros procesos, por ejemplo, en el proceso de devolución de un pedido.

![[subproceso_bpmn.png]]