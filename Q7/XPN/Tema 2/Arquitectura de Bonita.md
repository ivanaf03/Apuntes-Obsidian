[[Tema 2-Automatización de procesos]]

## Características de Bonita
Bonita es un motor de automatización que consta de un entorno propio de desarrollo. Permite modelar procesos, diseñar interfaces y crear un modelo de datos. Permite conectarse fácilmente a otros sistemas, como bases de datos, SIEs, servicios web, sistemas de correo, notificaciones, etc. 

Para todo esto dispone de un diseñador de procesos, un diseñador de interfaces, un portal de administración, una base de datos embebida para trabajar en modo desarrollo, que es H2, y un servidor web embebido, Apache Tomcat.

### Aplicaciones en Bonita
Con Bonita se pueden hacer aplicaciones con el Bonita UI Designer. Está basado en Angular y en el diseño WYSIWYG (What You See Is What You Get). Lo que ve el desarrollador es muy similar al resultado final, sin necesidad de tocar código.

Además, permite conectar el motor de automatización a aplicaciones externas a través de APIs de integración.

## Arquitectura general

![[arquitectura bonita.png]]

## Metodología recomendada
La documentación de Bonita recomienda:
1. Establecer los objetivos del proyecto.
2. Determinar el alcance de este.
3. Dibujar el diagrama de proceso.
4. Definir los detalles del proceso.
5. Diseñar la aplicación.
6. Hacer pruebas.
7. Desplegar la aplicación.
8. Integrar la aplicación en la organización.
