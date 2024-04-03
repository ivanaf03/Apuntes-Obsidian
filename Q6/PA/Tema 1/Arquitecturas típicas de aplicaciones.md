[[Tema 1-Introducción al desarrollo con frameworks modernos]]

## 1.Arquitecturas de aplicaciones
Algunas aplicaciones se pueden implementar por capas. Existen varias arquitecturas que siguen la separación en capas.
### 1.1.Arquitectura de aplicaciones nativas (arquitectura de referencia)
Se separa el frontend del backend. El frontend se compone de la interfaz gráfica y de una capa de acceso a servicios. Esta accede a través de la red a la capa de servicios en el backend, que ofrece funcionalidades implementadas en la capa modelo. La capa modelo está formada por la capa lógica de negocio y la capa de acceso a datos. La primera implementa las funcionalidades y la segunda se comunica con la base de datos.

![[arquitectura de referencia.png]]

### 1.2.Arquitectura de aplicación web del lado servidor con capa modelo local
El navegador hace peticiones por la red al servidor de aplicaciones. Este las recibe, las procesa y devuelve páginas HTML.

![[aplicacion web modelo local.png]]

### 1.4.Arquitectura de aplicación web del lado servidor con capa modelo remota
Es idéntica a la anterior, pero separando frontend de backend.

![[aplicacion web modelo remota.png]]

## 2.Aplicaciones web SPA
Una Single Page Application es una aplicación web formada por:
+ **Frontend:** JavaScript que se ejecuta en el navegador.
+ **Backend:** servicio generalmente en REST/JSON y capa modelo.

$\space$
![[aplicación web spa.png]]

### 2.1.Funcionamiento
Cuando el usuario introduce la URL de la aplicación en el navegador, este envía un GET con la página HTML base, el `index.html`, con referencias a JS. Se descarga el código JS, se ejecuta y pinta la UI.

La UI reacciona a los eventos del usuario y hace peticiones al `backend` a través de la capa de acceso a servicios. Además manipula el árbol DOM de la página con los datos devueltos por el servicio.

En el ámbito profesional, muchas aplicaciones combinan peticiones al navegador de páginas HTML con aplicaciones SPA.