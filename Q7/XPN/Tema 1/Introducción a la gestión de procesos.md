[[Tema 1-Modelado de procesos con BPMN]]

## Qué es un proceso?
Un proceso es el conjunto de actividades desarrolladas por diferentes actores utilizando los recursos y ordenadas según un flujo de trabajo. Su finalidad es conseguir un resultado concreto.

Las actividades no tienen por qué ejecutarse secuencialmente. El orden depende de las entradas del proceso.
$\space$
### Proceso y proyecto
Un proyecto es un esfuerzo temporal con un inicio y un fin determinados cuyo objetivo es crear un producto o un servicio únicos. Los proyectos no tienen como finalidad crear algo único, sino producir siempre el mismo resultado.

Por ejemplo, la fabricación de bicicletas es un proceso, ya que siempre se hacen de la misma forma. En cambio, cuando un cliente pide una aplicación software concreta se realiza un proyecto.
$\space$
### Ejemplo: proceso de compra de comida online
```
1. El cliente indica su dirección.
2. El cliente selecciona el restaurante.
3. La aplicación muestra todos los platos que ofrece el restaurante.
4. El cliente selecciona los platos que quiere.
5. El cliente confirma el pedido y realiza el pago.
6. El cliente indica si recoge el pedido o se entrega a domicilio.
7. La aplicación notifica al restaurante y, si es el caso, al repartidor.
8. El restaurante prepara el pedido y, si es el caso, el repartidor va a recogerlo.
9. El cliente o el reapartidor recogen el pedido.
```

En este caso las funcionalidades no están aisladas, sino que forman un flujo de trabajo o workflow. No sería buena idea modelarlo con diagramas de casos de uso. 
$\space$
## Modelado de procesos
Modelar consiste en seleccionar los elementos de la realidad que son relevantes para el sistema que se va a construir. Para modelar hay dos cosas imprescindibles:
+ Conocer la semántica y la sintaxis del lenguaje.
+ Ser capaces de identificar bien los elementos mediante la información que nos dan.

Un ejemplo de lenguaje de modelado de procesos es 