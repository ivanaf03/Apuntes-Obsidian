[[Tema 2-Automatización de procesos]]

## Eventos de inicio
Bonita soporta eventos de inicio de tipo:
+ Abstracto
+ Recepción de mensajes de otros procesos
+ Señal enviada por otro proceso o sistema
+ Temporal
+ Error

## Eventos temporales
Los eventos temporales se pueden activar con una condición temporal cíclica. Esta se puede indicar en minutos, horas, días, meses o años. Se suelen usar en procesos de facturación, nóminas, pagos periódicos, etc. Otra forma es activarlos con una fecha fija, por ejemplo, indicando que se lance 10 horas después de una tarea.

Para tener una mayor flexibilidad con las fechas, se pueden definir expresiones temporales en Groovy.