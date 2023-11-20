[[Tema 1-Introducción al desarrollo de aplicaciones empresariales]]

### Capas
Una capa es un software que proporciona servicios a otro software a través de una interfaz o contrato de servicio. La capa inferior es la encargada de proporcional el servicio y la superior de recibirlo.

Esto sirve para independizar el software. Permite escalabilidad y tolerancia a fallos. Además facilita el mantenimiento. Si sabemos en que capa está el fallo, solo habrá que comprobar el código de esta.

##### Ventajas
+ Los desarrolladores no necesitan conocer las tecnologías empleadas en otras capas.
+ Se puede desarrollar el software en paralelo. Lo primero es definir las interfaces. Una vez hecho esto, el trabajo de las capas es independiente.
+ Se facilita el mantenimiento.
+ Se facilita la escalabilidad y tolerancia a fallos, ya que pueden aumentarse los recursos solo en las capas donde sea necesario.

##### Riesgos
+ Software complejo.
+ Existen casos en los que el enfoque de capas no es la forma más óptima de trabajar.