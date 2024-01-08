[[Interfaces Persoa Máquina]]

## Patrón MVC
El patrón model-view-controller es un patrón de diseño software por capas. Se divide en:
+ **Modelo:** representa la capa de datos y la lógica de negocio de la aplicación. Contiene la representación interna de los datos y las operaciones que se pueden realizar sobre ellos. Notifica a las vistas sobre cambios en los datos, permitiendo que la interfaz de usuario se actualice en consecuencia.
+ **Vista:** es responsable de presentar la interfaz de usuario al usuario final. Muestra los datos provenientes del modelo y se actualiza automáticamente cuando los datos cambian. Generalmente, la vista en MVC puede contener cierta cantidad de lógica de presentación, aunque se espera que esta lógica sea mínima.
+ **Controlador:** maneja las interacciones del usuario y actúa como intermediario entre la vista y el modelo. Contiene lógica de presentación y lógica de negocio relacionada con las interacciones del usuario. Actualiza el Modelo en respuesta a las acciones del usuario y actualiza la Vista en consecuencia.

![[mvc vs mvp.png]]

### Comunicación
Sigue un flujo unidireccional. El controlador maneja las acciones del usuario y actualiza el modelo y la vista según sea necesario. La vista observa al modelo y se actualiza automáticamente cuando los datos cambian. 

### Ventajas
+ Separación clara de responsabilidades entre el modelo, la vista y el controlador.
+ Facilita la reutilización del código al separar la lógica de presentación y la lógica de negocio.
+ Mejora la modularidad y el mantenimiento del código al reducir el acoplamiento entre los componentes.

### Inconvenientes
+ La separación de responsabilidades puede ser difusa, especialmente en el controlador, que puede volverse complejo.
+ La comunicación unidireccional puede complicar la comprensión del flujo de datos en comparación con patrones más modernos como MVP.

## Patrón MVP
Es una evolución del patrón MVC, diseñado para mejorar la separación de preocupaciones y facilitar las pruebas unitarias en el desarrollo de software. Es también un patrón de diseño por capas, model-view-presenter. Se divide en:
+ **Modelo:** representa la capa de datos y la lógica de negocio de la aplicación. Contiene la representación interna de los datos y las operaciones que se pueden realizar sobre ellos. Se encarga de notificar a las vistas sobre cambios en los datos, generalmente a través de un mecanismo de observación o eventos. La independencia de la interfaz de usuario permite que el modelo pueda ser probado de manera aislada sin depender de la lógica de presentación.
+ **Vista:** es responsable de presentar la interfaz de usuario al usuario final. Difiere del MVC en que es pasiva y carece de lógica de presentación significativa. Observa cambios en el modelo y se actualiza automáticamente, reflejando cualquier cambio en los datos. Al no contener lógica de control es más fácil de probar, ya que su interacción con el presentador es principalmente a través de interfaces.
+ **Presentador:** actúa como un intermediario entre la vista y el modelo. Contiene la lógica de presentación y se encarga de manejar las interacciones del usuario. La comunicación entre la vista y el presentador es bidireccional, permitiendo que el presentador actualice la vista y maneje las acciones del usuario. Al tener la lógica de presentación separada, facilita las pruebas unitarias y mejora la modularidad del código.

![[mvc vs mvp.png]]

### Comunicación
Está diseñada para minimizar el acoplamiento. La vista observa al modelo y se actualiza automáticamente en respuesta a los cambios en los datos. El presentador, al manejar las interacciones del usuario, actualiza tanto el modelo como la vista según sea necesario. Este enfoque de comunicación facilita la mantenibilidad y flexibilidad.

### Ventajas
- Separación clara de responsabilidades entre el Modelo, la Vista y el Presentador.
- Facilita las pruebas unitarias al tener la lógica de presentación independiente.
- Mejora la modularidad y el mantenimiento del código al reducir el acoplamiento entre los componentes.

### Inconvenientes
- Puede generar una mayor cantidad de código debido a la estricta separación de responsabilidades.
- La comunicación bidireccional entre la vista y el presentador puede resultar compleja en algunos casos.

## Patrón BLoC (Business Logic Component) en Flutter
+ https://xurxodev.com/introduccion-al-patron-bloc/

![[patrón BLOC.png]]

##  Patrón Provider en Flutter
+ https://dev.to/cat_yena/patron-provider-en-flutter-4hf1

![[provider.png]]