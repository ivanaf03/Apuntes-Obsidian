[[Tema 1-Introducción al desarrollo con frameworks modernos]]

# 1.Arquitecturas de aplicaciones
## 1.1.Arquitectura de referencia
![[arquitectura de referencia.png]]

## 1.2. Arquitectura de aplicaciones nativas
![[arquitectura móvil.png]]

## 1.3.Arquitectura de aplicación web con capa modelo local
![[aplicacion web modelo local.png]]

El servidor recibe peticiones del navegador y devuelve páginas HTML.

## 1.4.Arquitectura de aplicación web con capa modelo remota
![[aplicacion web modelo remota.png]]

Lo mismo que la anterior, pero separa frontend de backend.

# 2.Aplicaciones web SPA
![[aplicación web spa.png]]
Una Single Page Application está compuesta por:
+ [>] *Frontend:* JavaScript en el navegador.
+ [>] *Backend:* servicio implementado en REST/JSON y una capa modelo.

## 2.1.Funcionamiento
Cuando el usuario introduce la URL de la aplicación en el navegador, este envía un GET con la página HTML correspondiente con referencias a JS. Se descarga el código JS, se ejecuta y pinta la UI.

La UI reacciona a los eventos del usuario y hace peticiones al `backend` a través de la capa de acceso a servicios. Además manipula el árbol DOM de la página con los datos devueltos por el servicio.

En el ámbito profesional, muchas aplicaciones combinan peticiones al navegador de páginas HTML con aplicaciones SPA.