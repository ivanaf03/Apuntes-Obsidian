[[Tema 10-Controles de servidor]]

## Definición de controles
Los controles son los elementos visuales de los web forms. Se definen desde la barra de herramientas o escribiendo el propio código. Se ejecutan del lado del servidor mediante el atributo `runat="server"`. Pueden mantener su estado mediante el view state con el atributo `ViewState`. 

Pueden ser:
+ HTML controls.
+ Web controls.

## System.Object.Control
Los controles heredan de `System.Object.Control`. Este contiene los atributos:
+ **ClientID:** identificador único.
+ **Controls:** colección de controles.
+ **EnableViewState:** true por defecto, indica si se mantiene el estado entre peticiones.
+ **ID:** identificador del control desde el cual se puede acceder desde el código.
+ **Parent:** referencia al padre del control, que puede ser la página u otro control.
+ **Visible:** indica si se renderiza el control.

Los métodos que contiene son:
+ **DataBind():** enlaza el control con un `DataSource`.
+ **FindControl():** busca un control entre el control y sus hijos.
+ **HasControls():** indica si el control tiene hijos.
+ **RenderControl():** lo llama ASP.NET y no se puede llamar directamente. Genera el HTML del control.

### HTML Controls
Se corresponden con los elementos del HTML estándar. Por defecto, mediante el servidor con CodeBehind no es posible acceder a sus propiedades. Se pueden transformar en controles de servidor mediante las propiedades `id` y `runat="server"`. 

### Web Controls
Son accesibles desde el lado del servidor. Tienen más funcionalidades que los controles de HTML. Son del estilo `<asp:nombre_control>`. Pueden generar uno o más elementos HTML al renderizarse. 

Tienen las propiedades:
+ **CssClass:** apunta a una clase CSS.
+ **Enabled:** determina si el usuario puede interactuar con él.
+ **TabIndex:** fija el orden de desplazamiento por la página con el tabulador.
+ **Tooltip:** renderiza un título para el componente.
+ **Visible:** determina si se envía el control al navegador.
+ **Propiedades de estilos:** se pueden definir el color de fondo, la altura, tamaño del texto, etc.