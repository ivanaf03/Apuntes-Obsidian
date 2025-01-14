[[Tema 15-Internacionalización]]

## Para qué sirven los recursos globales?
Sirven para almacenar recursos presentes en varias páginas del sitio web. Se almacenan en la carpeta `App_GlobalResources`, que debe estar en el directorio raíz. Los ficheros siguen el formato `<nombre>.<cod_cultura>.resx`.

### Creación de archivos de recursos globales
No se pueden generar automáticamente. Se hace de forma muy similar a los archivos locales, pero desde la carpeta raíz. 

## Acceso a recursos globales
Se puede acceder de dos formas:
+ Mediante localización explícita.
+ Mediante programación.

### Mediante localización explícita
Es idéntico a como se hace para recursos locales, pero `Class` es obligatorio. Indica el nombre del archivo de recursos globales.

![[loc_gl_explicita.png]]

### Acceso mediate programación
Se puede acceder a los elementos con el método genérico `protected object GetGlobalResourceObject(string className, string resourceKey);` o con propiedades estáticas, `Resources.[archivo_recursos_globales].[Clave];`.

```csharp
//Con el método
Button1.Text = GetGlobalResourceObject("Resource_Global", "Cancel").ToString();

//Propiedades estáticas
Button1.Text = Resources.Resource_Global.Cancel;
```

## asp:Localize
Para incluir bloques de texto se puede usar `<asp:Localize>`. No genera etiquetas extra HTML y es editable en la vista de diseño.

```csharp
<h3>
	<asp:Localize runat=server ID="LocWelcMess"
	Text="Welcome"
	meta:resourcekey="WelcomeMessage"/>
</h3>

// Renderiza
<h3>Welcome</h3>
```
