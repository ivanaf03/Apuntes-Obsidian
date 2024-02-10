[[Tema 1-Introducción al desarrollo con frameworks modernos]]

## Arquitectura de referencia
![[arquitectura de referencia.png]]

## Arquitectura de aplicaciones nativas
![[arquitectura móvil.png]]

## Arquitectura de aplicación web con capa modelo local
![[aplicacion web modelo local.png]]El servidor recibe peticiones del navegador y devuelve una página HTML.

## Arquitectura de aplicación web con capa modelo remota
![[aplicacion web modelo remota.png]]

## Aplicación web SPA
![[aplicación web spa.png]]
Una aplicación SPA está formada por:
+ **Frontend:** JavaScript en el navegador.
+ **Backend:** REST/JSON y capa modelo.

El servidor web aloja una página HTML mínima que contiene referencias a CSS y a JS. El navegador hace un GET a esa página, la parsea y accede al código JS, que pinta toda la UI de la aplicación.

La UI reacciona a los eventos del usuario y hace peticiones al backend a través de la capa de acceso a servicios. Además manipula el árbol DOM de la página con los datos devueltos por el servicio.

En el ámbito profesional, muchas aplicaciones combinan peticiones al navegador de páginas HTML con aplicaciones SPA.