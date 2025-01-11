[[Tema 9-Web Forms]]

## Cómo funciona el modelo de eventos?
ASP.NET permite añadir controles a un formulario y decidir a qué eventos se responde. Cada evento se gestiona con un método. El flujo es el siguiente:
1. Cuando la página se ejecuta por primera vez, ASP.NET crea los objetos necesarios, ejecuta el código de inicialización, renderiza el HTML y lo envía al cliente. Los objetos se liberan de la memoria del servidor.
2. Cuando el usuario hace algo que lanza un postback, la página se envía con todos los datos del formulario.
3. ASP.NET intercepta la página y crea de nuevo todos los objetos.
4. ASP.NET comprueba que operación lanzó el postback y lanza los eventos correspondientes. Esto ejecuta operaciones del lado del servidor normalmente.
5. Se renderiza la página modificada a HTML y se devuelve al cliente. Los objetos se liberan del servidor y siempre se repite el proceso.

## Postbacks automáticos
Los postback automáticos ocurren cuando el usuario hace una acción en la pantalla, pero que no necesariamente pulsa un botón de submit adicional, por ejemplo, seleccionar en un checkbox una opción. Para ello, los componentes de ASP.NET tienen una propiedad, `AutoPostBack`, que se puede poner a true. Esto añade una función JS llamada `_doPostBack()` al HTML. Además, añade dos campos que la función utiliza para pasar información al servidor: el id del evento, `eventTarget` y parámetros adicionales, `eventArgument`. La función establece los valores con la información del evento y envía el formulario.

Esto solo funciona en web controls, no está disponible con HTML server controls.


