[[Tema 1-Creación de interfaces]]

### Patrón MVP
El patrón MVP (Modelo-Vista-Presentador) es un patrón de diseño de arquitectura de software que se utiliza comúnmente en el desarrollo de aplicaciones de software para separar las preocupaciones y organizar el código de manera más eficiente. El objetivo principal del patrón MVP es lograr una mayor modularidad, mantenibilidad y pruebas unitarias en una aplicación.

El patrón MVP consta de tres componentes principales:
1. **Modelo (Model):** El Modelo representa la capa de datos y lógica de negocio de la aplicación. Contiene las estructuras de datos, la lógica para acceder a los datos (como consultas a una base de datos) y la lógica de procesamiento de datos. El Modelo es independiente de la interfaz de usuario y no tiene conocimiento de cómo se presenta la información.
2. **Vista (View):** La Vista es la capa de presentación de la aplicación. Es responsable de mostrar la información al usuario y recoger las interacciones del usuario, como clics de botón o entrada de datos. En el contexto del patrón MVP, la Vista es pasiva y no contiene lógica de negocio. En su lugar, se limita a mostrar los datos proporcionados por el Presentador y enviar eventos de usuario al Presentador.
3. **Presentador (Presenter):** El Presentador actúa como un intermediario entre el Modelo y la Vista. Tiene varias responsabilidades:
	+ Control de la lógica de presentación: Decide cómo se debe presentar la información al usuario y cómo se deben manejar las interacciones del usuario en la interfaz de usuario.
	+ Comunicación con el Modelo: Se comunica con el Modelo para obtener los datos necesarios y realizar cualquier operación lógica en los datos antes de mostrarlos en la Vista.
	 + Actualización de la Vista: Toma los datos del Modelo y los formatea adecuadamente para que se muestren correctamente en la interfaz de usuario. Luego, actualiza la Vista con estos datos.
	+ Manejo de eventos del usuario: Escucha los eventos generados por el usuario en la Vista y responde a ellos tomando las acciones apropiadas. Por ejemplo, puede realizar validaciones antes de enviar datos al Modelo o actualizar la Vista en respuesta a una acción del usuario.

El flujo de trabajo típico en el patrón MVP es el siguiente:
1. El usuario interactúa con la Vista, generando eventos de usuario.
2. El Presentador escucha estos eventos y los procesa según sea necesario.
3. El Presentador se comunica con el Modelo para obtener o actualizar datos.
4. El Presentador formatea los datos y actualiza la Vista con la información.
5. La Vista muestra los datos actualizados al usuario.