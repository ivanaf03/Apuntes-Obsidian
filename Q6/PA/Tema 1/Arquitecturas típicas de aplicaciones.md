[[Tema 1-Introducción al desarrollo con frameworks modernos]]
$\space$
## 1.Arquitectura en capas
La arquitectura en capas es un diseño de software que organiza el sistema en niveles lógicos o capas, donde cada capa tiene una responsabilidad específica y se comunica con las adyacentes a través de interfaces bien definidas. Sin embargo, dependiendo del tipo de aplicación, esta arquitectura puede tener variantes.
$\space$
### 1.1.Aplicaciones nativas (arquitectura de referencia de la asignatura)
Separa frontend y backend. El frontend se compone de interfaz gráfica y capa de acceso a servicios. La interfaz gráfica se comunica con el usuario final y la capa de acceso a servicios accede a través de la red a la capa de servicios del backend, que ofrece las funcionalidades implementadas en la capa modelo. 

La capa modelo está compuesta por la capa de lógica de negocio y la capa de acceso a datos. La capa de lógica de negocio es la que implementa las funcionalidades y la capa de acceso a datos es la que se comunica con la BBDD.

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
Una Single Page Application es una aplicación web formada por un frontend en JavaScript que se ejecuta en el navegador y un backend, normalmente implementado con servicios REST y JSON y una capa modelo a la que accede el frontend.

![[aplicación web spa.png]]
$\space$
### 2.1.Funcionamiento
Cuando el usuario introduce la URL de la aplicación en el navegador, este envía un GET que devuelve la página raíz de la aplicación, que suele llamarse `index.html`. Contiene llamadas a funciones JavaScript. Se descarga el código, se ejecuta y este pinta la interfaz. 

La interfaz de usuario, UI, reacciona ante eventos que este produce y hace las peticiones al backend necesarias a través de la capa de acceso a servicios. Esto modifica el árbol DOM con los datos proporcionados por los servicios.

Profesionalmente, muchas aplicaciones combinan peticiones al navegador de páginas HTML con aplicaciones SPA.