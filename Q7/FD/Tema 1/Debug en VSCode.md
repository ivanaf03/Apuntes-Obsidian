[[Tema 1-Entornos integrados de desarrollo]]

## Breakpoints
Los breakpoints permiten detener el código y hacer algo con el en lugares concretos. Existen varios tipos de breakpoints:
+ **Line breakpoints:** pausan la ejecución en una línea concreta de código.
+ **Conditional breakpoints:** pausan la ejecución si se cumple una condición determinada.
+ **Data breakpoints:** pasan la ejecución cuando una variable toma cierto valor.
+ **Logpoints:** muestra mensajes en la consola de debug sin parar la ejecución.
+ **Triggered breakpoints:** se lanzan cuando otro breakpoint se alcanza.

### Hot Code Replace
> [!abstract] Definición de Hot Code Replace
> El Hot Code Replace (HCR) es una técnica de debugging que permite añadir cambios a la JVM sin necesidad de reiniciar la aplicación.

Es muy útil para realizan pequeños arreglos en medio del debug. 

## Call stack y restart frame
El call stack muestra la lista de métodos que están activos en un punto concreto del programa. Permite seguir la traza de ejecución y conocer como se ha llegado a la situación actual en el debug. Se puede navegar por el call stack en medio del debug para ver como se comportan las variables y las expresiones a lo largo del código.

El restart frame permite reiniciar la ejecución de un frame concreto del call stack. Ayuda a optimizar el tiempo durante el debug del call stack.

## Servidores de aplicaciones
VSCode no incluye servidores de aplicaciones internos. Se deben configurar, habilitar por línea de comandos y configurar adecuadamente el debugger para que pueda usarse en ellos. Dos extensiones muy útiles para trabajar con servidores de aplicaciones son Community Server Connectors y Spring Boot DashBoard.

Una vez arrancado el debug, se muestra en la vista de variables los valores que tiene cada una de ellas en la instancia que corre en el servidor.

## Otros tipos de depuración
Para debuggear el frontend, hay que crear un fichero llamado `launch.json` y elegir el navegador que queramos en el puerto de desarrollo. Al correr el servidor de desarrollo y realizar acciones en el frontend, cuando haya un caso que active un breakpoint el código parará.

### Debug en contenedores
La extensión de Docker configura el fichero `launch.json` para pode debuggear el proyecto corriendo en un contenedor de aplicaciones. Además incluye un proveedor de configuración para indicar como lanzar la aplicación mediante configuraciones en el `launch.json`.

