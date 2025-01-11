[[Tema 10-Controles de servidor]]

## Qué son los controles de validación?
Los controles de validación son elementos ocultos que validan las entradas de datos comparándolos con algún patrón. Se puede hacer tanto desde el lado cliente como del lado servidor.

### Validación del lado cliente
Avisa al usuario antes de enviar los datos al servidor. Genera JS en el cliente, pero es más rápido que hacer la validación en el servidor. Los controles de validación de ASP.NET lo hacen por defecto.

### Validación del lado servidor
Se repite la validación en el servidor por temas de seguridad. La validación se hace despues del `Page_Load`, pero antes de otros eventos, por lo que se puede comprobar si la página es válida con `Page.IsValid`.

## Lista de controles
ASP.NET proporciona 6 controles:
+ **RequiredFieldValidator:** comprueba que el formulario no esté vacío.
+ **RangeValidator:** comprueba que el valor esté dentro de un rango.
+ **CompareValidator:** comprueba que el valor sea mayor, menos o igual que otro.
+ **RegularExpressionValidator:** comprueba que el valor sigue la expresión regular.
+ **CustomValidator:** permite definir una validación personalizada del lado cliente y del lado servidor.
+ **ValidationSummary:** muestra los mensajes de error lanzados por otros controles.

## Clase BaseValidator
Los controles de validación extienden la clase `BaseValidator`. Define la funcionalidad básica de un control de validación:
+ **ControlToValidate:** control que se va a validar.
+ **Display:** puede ser estático o dinámico el espacio que reserva para mostrar un mensaje de error.
+ **EnableClientScript:** especifica si se realiza validación del lado cliente.
+ **Enabled:** permite habilitar o deshabilitar el validador.
+ **ErrorMessage:** cadena de errores del `ValidationSummary`.
+ **Text:** cadena que se muestra si falla la validación.
+ **IsValid:** indica si el valor es válido.
+ **SetFocusOnError:** cambia el focus del navegador al error.
+ **ValidationGroup:** permite agrupar validadores.
+ **Validate():** actualiza el valor de `IsValid`. Se llama a este método al hacer un postback con `CausesValidation="true"`.