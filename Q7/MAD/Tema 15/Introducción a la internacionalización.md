[[Tema 15-Internacionalización]]

## Qué es la internacionalización?
> [!abstract] Definición de internacionalización
> La internacionalización es el proceso de diseñar un producto de forma genérica para facilitar el proceso de localización sin necesidad de modificar el componente central.

### Internacionalización en .NET
En .NET se internacionaliza con el namespace `System.Globalization`. Contiene clases que dan soporte a idiomas, formatos numéricos, monedas, etc.

## Estándares y culturas
Los nombres siguen el estándar RFC1766. El formato es `<cod_idioma>-<cod_region>`. Por ejemplo, en-US. La cultura neutral solo indica el idioma, por ejemplo "en", y la cultura específica indica la región y da información para el formato, por ejemplo "FR-fr". 

### Cultura invariante
La cultura invariante es de la raíz de todas las culturas. Sirve para almacenar datos que son independientes de la cultura, por ejemplo, los que no se muestran al usuario final. Se hace mediante `CultureInfo.InvariantCulture`. 

### CultureInfo
La clase `System.Globalization.CultureInfo` proporciona información sobre una cultura concreta. Permite acceder a objetos concretos de la cultura con operaciones específicas para ellos. 

Contiene las propiedades `CurrentCulture`, que determina los resultados que dependen del país y región y su valor es una cultura específica; y `CurrentUICulture`, que determina el idioma de las cadenas de texto de la UI y su valor puede ser simplemente el idioma.

## Archivos de recursos
Los archivos de recursos almacenan diferentes tipos de recursos, como cadenas de texto o imágenes que se utilizan en la aplicación. Son archivos XML con extensión `.resx` formados por pares clave-valor. La clave no distingue mayúsculas y minúsculas. Debe haber un archivo por idioma o por región. 

Pueden ser:
+ Locales.
+ Globales.

Se pueden manejar cómodamente mediante la extensión `ResXResourceManager`. 