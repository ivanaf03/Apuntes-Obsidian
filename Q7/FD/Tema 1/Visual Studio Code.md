[[Tema 1-Entornos integrados de desarrollo]]

## Qué es VSCode?
VSCode es un editor de código abierto muy ligero desarrollador por Microsoft. Soporta una cantidad inmensa de lenguajes de programación y extensiones. Está hecho en Electron, lo que permite compatibilidad con múltiples sistemas operativos e incluso con el navegador.

### Espacio de trabajo en VSCode
> [!abstract] Definición de workspace
> Un workspace es una colección de carpetas abiertas en una instancia del IDE.

Normalmente, se abre solo una, pero VSCode permite abrir varias mediante los Multi-root workspaces.

Se puede configurar cada workspace con características específicas. Es útil, por ejemplo, para la configuración del debugger. Los workspaces también guardan el estado de la UI, con los archivos que tenía abiertos el desarrollador. Además permite seleccionar que extensiones tiene activas.

## Vistas de VSCode
> [!abstract] Definición de vista
> Una vista es un contenedor que muestra diferentes contenidos en el IDE.

Permiten ver diferentes tipos de contenidos:
+ **Vistas en árbol:** muestran estructuras de datos en forma de árbol, por ejemplo, el explorador de archivos.
+ **Vistas de bienvenida:** muestran tutoriales o información, por ejemplo, la vista de bienvenida de la extensión de GitHub.
+ **Vistas web:** muestran contenido web dentro del editor, por ejemplo, la extensión de previsualización de markdown.

Permiten mediante view actions interactuar al usuario con ellas. Además, el usuario puede moverlas entre los contenedores como quiera.

### Editor
El editor es una vista especial que sirve para modificar un elemento de datos. Es el lugar donde se trabaja.

### Vista de problemas
Otra vista importante es la vista de problemas. Permite ver los errores, warnings y mensajes informativos del workspace. Se sitúa en el panel, debajo del editor. 

Los problemas se agrupan por fichero para que sea más fácil encontrarlos. También se pueden filtrar por:
+ **Tipo:** separar por errores, warnings o info.
+ **Texto:** filtrar por palabras clave.
+ **Fuente:** filtrar por herramientas, como TypeScript, ESLint, etc.
+ **Excluir archivos:** no mostrar los archivos seleccionados.

### Vista de documentación
Se instala mediante la extensión Docs View. Muestra la documentación en la vista en lugar de en un pop-up.

## Perfiles
VSCode ofrece un montón de configuraciones y extensiones para modificar como quiera el usuario su entorno. Mediante los perfiles, se pueden tener diferentes personalizaciones de la UI en diferentes proyectos o workspaces. Se pueden exportar e importar estas configuraciones. 

La configuración por defecto, sin haber creado perfiles, se guarda en el default profile. Mediante los perfiles parciales se pueden configurar un pequeño conjunto de cosas mientras que el resto se sacan del default profile.

### Java general profile
Este perfil está diseñado para trabajar con Java de forma cómoda. Viene con el "Extension pack for Java". Esta extensión trae:
+ Debugger configurado para Java.
+ IntelliSense y soporte para el lenguaje.
+ IntelliCode.
+ Maven for Java.
+ Project Manager for Java.
+ Test runner for Java.

## Barras de navegación
VSCode tiene 3 barras principales:
+ **Barra de actividad:** es la barra grande de la izquierda. Muchas de las extensiones se acoplan a ella para facilitar el acceso a los contenedores de las vistas correspondientes.
+ **Barras laterales:** existen dos, la principal y la secundaria. Son un conjunto de vistas, por ejemplo, el explorador de archivos, la vista de Maven, etc.
+ **Barra de estado:** contiene información y acciones relacionadas con el espacio de trabajo. Se sitúa en la parte de abajo del IDE. A la izquierda sitúa los ítems que afectan a todo el workspace, como los warnings y a la derecha ítems relacionados con el editor, como el lenguaje, el espaciado, la línea y columna...