[[Tema 9-Web Forms]]

## Etapas de procesado de un web form
![[procesado_web_form.png]]

### Inicialización de la página
ASP.NET genera todos los controles definidos en el `.aspx`. Si no es la primera vez que se solicita la página, se aplica la información del view state a los controles. Finalmente, se lanza el evento `Page.Init`.

### Inicialización del código de usuario
Se lanza el evento `Page.Load`. La mayoría de páginas lo utilizan para inicializar los controles. Las inicializaciones aquí se consideran cambios en el view state. Este evento se lanza siempre, ya sea la primera vez que se carga la página o tras un postback. Para ver si es la primera vez, se puede utilizar la propiedad `IsPostBack`.

```csharp
protected void Page_Load(object sender, EventArgs e) 
{ 
	if (!IsPostBack) 
	{ 
		//It's safe to initialize the controls for the first time. 
		FirstName.Text = "Enter your name here"; 
	} 
}
```

### Validación
ASP.NET incluye controles de validación automáticos para mostrar mensajes de error antes entradas inválidas del usuario. Se lanzan siempre antes que el resto de tipos de eventos. No suele ser necesario responder a estos eventos, basta con consultar la propiedad `Page.IsValid` en otros manejadores de eventos, por ejemplo, en el `Page_Load`.

### Gestión de eventos
Una vez cargada y validada la página, se disparan todos los eventos que hubo desde el último postback. Pueden ser:
+ **De respuesta inmediata:** click en un control que lance un postback.
+ **De cambio:** eventos que se activan automáticamente si se establece `AutoPostBack=true`. De lo contrario, esperan a la próxima vez que se envía la página.

### Cleanup
Una vez se renderiza la página a HTML, se lanza el evento `Page.Unload`.