[[Tema 15-Internacionalización]]

## Indicar la cultura
La cultura se puede indicar a la aplicación de 3 formas:
+ Mediante configuración.
+ A nivel de página.
+ Mediante programación.

Puede usarse el valor `auto` para que sea el navegador del usuario el que selecciona la cultura.

### Mediante configuración
Se puede indicar en el `web.config`.

```xml
<configuration>
	<system.web>
		<globalization
		uiCulture="..."
		culture="..." />
	</system.web>
</configuration>
```

### A nivel de página
Se puede indicar en las páginas con la directiva `Page`.

```csharp
<%@Page UICulture="..." Culture="..." %>
```

### Mediante programación
Puede ser interesante modificar la cultura en base a datos de la BBDD, por ejemplo. Para ello hay que cambiar el comportamiento por defecto mediante el método `InitializeCulture()`. 

```csharp
using System.Globalization;
using System.Threading;

...

public partial class MainPage : System.Web.UI.Page
{
    ...

    protected override void InitializeCulture()
    {
        // establecer la cultura en inglés (EE. UU.)
        CultureInfo cultureInfo = new CultureInfo("en-US");
        Thread.CurrentThread.CurrentCulture = cultureInfo;
        Thread.CurrentThread.CurrentUICulture = cultureInfo;
    }

    ...
}

```

Se tiene que hacer esto en todas las páginas. No se puede hacer sobre la página maestra porque no hereda de `System.Web.UI.Page`, por tanto, no se puede sobrescribir el método. La solución es crear una clase hija que sobrescriba el método y que todas las páginas hereden de ella.

```csharp
using System.Threading;
using System.Globalization;

namespace Es.Udc.DotNet.MyApp.HTTP.Session
{
    public class SpecificCulturePage : Page
    {
        protected override void InitializeCulture()
        {
            // leer el idioma y el país (podría ser desde una base de datos)
            String language = "es"; // idioma español
            String country = "ES";  // país España
            String culture = language + "-" + country;

            // establecer la cultura específica
            CultureInfo cultureInfo = CultureInfo.CreateSpecificCulture(culture);
            Thread.CurrentThread.CurrentCulture = cultureInfo;
            Thread.CurrentThread.CurrentUICulture = cultureInfo;
        }
    }
}

----------

using System.Threading;
using System.Globalization;
using Es.Udc.DotNet.MyApp.HTTP.Session;

namespace Es.Udc.DotNet.MyApp.Pages
{
    public partial class APage : SpecificCulturePage
    {
        // lógica adicional aquí
        ...
    }
}
```