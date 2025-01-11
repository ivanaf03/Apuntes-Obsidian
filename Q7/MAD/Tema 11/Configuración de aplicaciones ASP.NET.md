[[Tema 11-Aplicaciones ASP.NET]]

## Cómo se hace la configuración?
Se realiza mediante archivos XML. Se puede modificar en cualquier momento, sin reiniciar la aplicación. 

Se hace en los ficheros:
+ machine.config
+ web.config

### Machine.config
Se guarda en los ficheros de framework, no en el proyecto. Permite definir secciones soportadas en ficheros de configuración, configura el proceso que sigue ASP.NET, registra proveedores, etc. Junto a él se añade un fichero `web.config` con información complementaria.

Todas las aplicaciones de la máquina heredan las configuraciones de estos archivos. Cuando se realiza el despliegue, algunas configuraciones se cambian por las de un fichero propio, el `ApplicationHost.config`.

### Web.config
Permite añadir información a cada aplicación concreta. Además, permite añadir en cada subdirectorio del directorio raíz un archivo que complemente la configuración.

Define una serie de elementos con etiquetas XML:
+ **location:** permite especificar mediante el atributo `path` la ruta donde se redefinen partes de la configuración.
+ **system.web:** contiene un esquema fijo con las opciones de configuración de ASP.NET.
+ **appSettings:** define pares clave valor que sirven, por ejemplo, para definir rutas. Se puede acceder mediante `ConfigurationManager.AppSettings["clave"]`.
+ **connectionStrings:** define cadenas de conexión a base de datos. También se puede acceder con `ConfigurationManager.ConnecctionStrings["clave"].toString()`.
+ **Secciones personalziadas:** se pueden personalizar secciones. Se leen con `ConfiguratioSettings.GetSection("section_name")`.

A mayores, el `web.config` guarda configuración de valores para toda la aplicación en el archivo `Properties/Settings.settings`. 