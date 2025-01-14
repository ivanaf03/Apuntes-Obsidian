[[Tema 15-Internacionalización]]

## Para qué sirven los recursos locales?
Sirven para almacenar recursos de páginas específicas. Se almacenan en las carpetas `App_LocalResources`. Siguen el formato `<NombreWebForm>.aspx.<cod_cultura>.resx`. No se especifica ningún código de cultura, este será el archivo por defecto. 

### Creación de archivos de recursos locales
Se pueden crear desde la vista de diseño o desde el explorador de soluciones. Esto añadirá, por ejemplo, `meta:resourcekey="Label1Resource1"` al componente `Label1`.

## Acceso a archivos de recursos locales
Se puede acceder de 3 formas:
+ Localización implícita.
+ Localización explícita.
+ Mediante programación.

### Localización implícita
Se hace mediante el atributo `meta:resourcekey`. Para utilizarla, se sigue el formato `Resource_key.Property`. Por ejemplo, `Label1Resource1.Text` para acceder al texto de la etiqueta.

### Localización explícita
Se utiliza una expresión del tipo `<%$ Resources: Class , Resource_ID %>` para asociar cada propiedad de un control con un nombre en el archivo de recursos. Poner `Class` es opcional y si se omite se usa el archivo de recursos local asociado a la página. 

![[loc_explicita.png]]

### Acceso mediante programación
Se puede acceder a los ficheros de recursos locales con el método `GetLocalResourceObject(string resourceKey)`. Por ejemplo:

```csharp
protected void Page_Load(object sender, EventArgs e) 
{
	Button1.Text = GetLocalResourceObject("Button1_Texto").ToString(); 
}
```

Se puede activar la generación de código y acceder a los valores mediante propiedades estáticas.

![[acceso_programacion.png]]

