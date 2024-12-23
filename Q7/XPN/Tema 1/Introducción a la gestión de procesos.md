[[Tema 1-Modelado de procesos con BPMN]]

## Qué es un proceso?
> [!abstract] Definición de proceso
> Un proceso es el conjunto de actividades desarrolladas por diferentes actores utilizando determinados recursos, ordenadas por un flujo de trabajo, que tiene como objetivo obtener un resultado concreto.

Las actividades no tienen por qué seguir un flujo de trabajo secuencial, el orden puede depender de las entradas que recibe el proceso.

### Proceso vs proyecto
> [!abstract] Definición de proyecto
> Un proyecto es un esfuerzo temporal con un inicio y un fin determinados, cuyo objetivo es crear un producto o dar un servicio único.

Se diferencian de los procesos en la finalidad. El objetivo de los procesos es siempre producir el mismo resultado. Los proyectos tratan de crear algo único. 

Por ejemplo, la fabricación de bicicletas es un proceso, ya que para producir el mismo modelo de bicicleta siempre se siguen los mismos pasos. En cambio, las aplicaciones software son proyectos.

### Ejemplo de proceso: compra de comida online
La compra de comida online en una aplicación siempre sigue los mismos pasos:
1. El cliente indica su dirección.
2. El cliente selecciona el restaurante.
3. La aplicación muestra todos los platos que ofrece el restaurante.
4. El cliente selecciona los platos que quiere.
5. El cliente elige si recoge el pedido y lo recibe a domicilio.
6. El cliente confirma el pedido.
7. El cliente tramita el pago.
8. La aplicación modifica el restaurante y al repartidor, si hay envío.
9. El restaurante prepara el pedido y el repartidor, si hay envío, se prepara para recogerlo.
10. El cliente o el repartidor recogen el pedido.

## Modelado de procesos
A parte de implementar funcionalidades aisladas, cuando un software tiene que ejecutar un proceso debe seguir un flujo de trabajo o workflow para que cada una de ellas se ejecute en el momento adecuado por el usuario correspondiente. Es mala idea modelar esto con diagramas de casos de uso.

> [!abstract] Definición de modelar
> Modelar consiste en seleccionar los elementos de la realidad que son relevantes en el sistema que se va a construir.

Para modelar correctamente es necesario conocer la sintaxis y semántica del lenguaje de modelado y identificar los elementos relevantes a partir del contexto y la información dados. Un ejemplo de lenguaje de modelado es BPMN.