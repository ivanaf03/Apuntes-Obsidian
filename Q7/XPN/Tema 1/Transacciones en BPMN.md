[[Tema 1-Modelado de procesos con BPMN]]

## Qué es una transacción?
> [!abstract] Definición de transacción
> Una transacción es un conjunto de operaciones que se ejecutan de manera conjunta y atómica, garantizando que se cumplan de forma completa y coherente. Si alguna de las operaciones falla, todas se revierten para mantener la integridad de los datos.

### Transacciones en BPMN
Para revertir esos cambios en BPMN se definen actividades de compensación. Se definen en todos los casos en los que puede fallar una transacción y dejar el proceso en un estado inconsistente.

![[compensacion_bpmn.png]]
