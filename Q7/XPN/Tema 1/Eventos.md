[[Tema 1-Modelado de procesos con BPMN]]

## Qué es un evento?
> [!abstract] Definición de evento
> Los eventos son los diferentes hitos que hay en un proceso. Expresan algo que ocurre en un punto concreto del workflow del proceso.

Al ser hitos, no tienen duración ni trabajo asociado. No tienen ninguna implementación asociada.

Todo proceso tiene al menos un evento de inicio y uno de fin. Si tiene más de un evento de inicio, estos deben ser compatibles entre sí.

## Tipos de eventos
Los eventos pueden ser:
+ De inicio
+ De fin
+ Intermedios

### Evento de inicio abstracto
El evento de inicio abstracto señala el inicio de una instancia del proceso. Solo puede haber uno, ya que si hubiera dos, al ejecutar una instancia del proceso el motor de automatización no sabría cual elegir.

![[inicio_abstracto_bpmn 1.png]]

### Evento de inicio temporal
El evento de inicio temporal se lanza cuando se cumple la condición temporal asociada, que puede ser desde una condición de periodicidad hasta una fecha y hora fija.

![[evento_temporal_bpmn.png]]

### Evento de inicio condicional
El evento de inicio condicional se lanza cuando se cumple una condición o una regla externa. 

![[evento_condicional.png]]

### Evento de inicio asociado a una señal
Las señales permiten a los procesos comunicarse entre ellos. Funcionan de forma similar a las señales de los procesos en los sistemas operativos. Los eventos de inicio asociados a estas se disparan cuando se genera la señal que llevan asociada en la configuración

![[evento_signal.png]]

### Eventos de fin

![[eventos_fin.png]]

### Eventos intermedios

![[eventos_intermedios.png]]

Los eventos intermedios asociados a tareas son útiles cuando los procesos tienen cierta duración. Un ejemplo es cuando se compra un coche nuevo y no queda stock. Algunas empresas envían notificaciones al cliente sobre el estado del coche en cada paso del proceso. 

No interrumpen la ejecución del workflow principal.

![[proceso_evento_intermedio_bpmn.png]]