[[Tema 1-Modelado de procesos con BPMN]]

## Qué es un proceso?
Un proceso es el conjunto de actividades desarrolladas por diferentes actores utilizando ciertos recursos, ordenadas según un flujo de trabajo, cuyo fin es obtener un resultado concreto. 

Las actividades no tienen por qué ejecutarse de forma secuencial. El orden puede variar según las entradas del proceso.

### Proceso y proyecto
Un proyecto es un esfuerzo temporal con inicio y fin definidos que busca crear un producto o un servicio únicos. Los procesos son repetitivos. 

Por ejemplo, para la fabricación de bicicletas siempre se siguen los mismos pasos, es decir, el mismo proceso. Por otro lado, cuando un cliente pide una aplicación software concreta se realiza un proyecto.

### Ejemplo de un proceso: compra de comida online
```
El cliente comienza el proceso indicando su dirección. A continuación, el cliente selecciona un restaurante. Después, en una pantalla que muestra todos los platos que ofrece ese restaurante, selecciona los que quiere comprar. A continuación confirma su pedido y completa el pago. Al hacer un pedido, el cliente puede indicar si recogerá el pedido en el restaurante o si necesita reparto a domicilio. Una vez completado el pago, la aplicación notifica el nuevo pedido al restaurante y, si es el caso, al repartidor que lo tiene que ir a recoger. El restaurante prepara el pedido. Mientras, si es el caso, el repartidor se desplaza a recogerlo. Cuando el pedido está preparado, bien el cliente o bien el repartidor lo recogen. Si hay reparto a domicilio, consideramos que el cliente recoge el pedido en el momento en que el repartidor se lo entrega.
```

Para este ejemplo no es buena idea utilizar un diagrama de casos de uso o un diagrama de secuencia, ya que las funcionalidades no están aisladas, sino que forman un proceso. El software debe garantizar que las actividades siguen un workflow o flujo de trabajo y que se ejecuten por el usuario correspondiente.

## Modelado de procesos
El modelado se basa en recoger los elementos de la realidad que son relevantes en el sistema que se va a construir. Para modelar correctamente necesitamos:
+ Conocer la semántica y sintaxis del lenguaje de modelado usado.
+ Identificar correctamente los elementos a partir de la información que nos dan.

En esta asignatura se usa BPMN (Business Process Management Notation).