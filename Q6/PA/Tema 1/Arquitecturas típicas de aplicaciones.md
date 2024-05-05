[[Tema 1-Introducción al desarrollo con frameworks modernos]]
$\space$
## 1.Arquitectura en capas
Algunas aplicaciones siguen la arquitectura por capas. Dependiendo de muchos factores, la arquitectura en capas varía un poco de unas aplicaciones a otras.
$\space$
### 1.1.Aplicaciones nativas (arquitectura de referencia de la asignatura)
Se separa el frontend del backend. El frontend está compuesto por la interfaz gráfica y la capa de acceso a servicios. Esta última accede a través de la red a la capa de servicios del backend, que ofrece las funcionalidades implementadas en la capa modelo.  La capa modelo se compone por la capa de lógica de negocio, que implementa las funcionalidades, y la capa de acceso a datos, que se comunica con la base de datos.

![[arquitectura de referencia.png]]
$\space$
### 1.2.Aplicaciones web del lado servidor con capa modelo local
Desde un navegador se hacen peticiones por la red al servidor de aplicaciones. Este las recibe, las procesa y devuelve páginas HTML.

![[aplicacion web modelo local.png]]
$\space$
### 1.3.Aplicaciones web del lado servidor con capa modelo remota
Funciona de forma idéntica a la anterior, pero separa el frontend y el backend.

![[aplicacion web modelo remota.png]]
$\space$
## 2.Aplicaciones web SPA
Una Single Page Application es una aplicación web formada por frontend en JavaScript que se ejecuta en el navegador y un backend, normalmente implementado con servicios REST y JSON y una capa modelo a la que accede el frontend.

![[aplicación web spa.png]]
$\space$
### 2.1.Funcionamiento
Cuando un usuario introduce la URL de la aplicación en el navegador, ente envía una petición GET que devuelve la página raíz de la aplicación, típicamente el `index.html`, que contiene llamadas a funciones JavaScript. Se descarga el código JS, se ejecuta y pinta la interfaz.

La UI reacciona antes los eventos del usuario y hace peticiones al backend a través de la capa de acceso a servicios. Esto modifica el árbol DOM gracias a los datos devueltos por el servicio.

Profesionalmente, muchas aplicaciones combinan peticiones al navegador de páginas HTML con aplicaciones SPA.