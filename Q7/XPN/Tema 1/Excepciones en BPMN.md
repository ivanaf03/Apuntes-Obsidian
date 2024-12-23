[[Tema 1-Modelado de procesos con BPMN]]

## Qué es una excepción?
> [!abstract] Definición de excepción
> Una excepción es una situación excepcional que implica tener que interrumpir el workflow normal del proceso y tomar medidas alternativas.

### Excepciones en BPMN
En BPMN las excepciones se pueden capturar y tratar como un camino alternativo en la tarea en la que se producen.

![[excepcion_bpmn.png]]

![[excepcion_bpmn_2.png]]

El problema de las excepciones en los motores de automatización es que si ocurre un error no recuperable y hubo cambios no confirmados, no sirve solamente con hacer un rollback. Los sistemas externos pueden quedar en un estado inconsistente si hubo alguna transacción completada.