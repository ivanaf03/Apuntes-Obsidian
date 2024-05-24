[[Tema 3-Arquitecturas centradas en la independencia de componentes]]
$\space$
## 1.Qué es un cliente-servidor distribuido?
El cliente-servidor puede ser distribuido. Cada funcionalidad se implementa en un único componente de un único servidor o pueden estar todas las funcionalidades en todos los servidores. 
$\space$
### 1.1.Ventajas e inconvenientes
El cliente-servidor distribuido:
+ [p] Separa las tareas de gestión y las funcionalidades, lo que mejora el rendimiento y la escalabilidad.
+ [c] Es difícil predecir como será el reparto de carga.
$\space$
### 1.2.Tipos de clientes
Los clientes pueden ser:
+ **Pesados:** representan la interfaz y contienen parte de la lógica de algunos servicios. Esto permite aprovechar la capacidad de procesamiento en los clientes, pero el problema es que el despliegue y mantenimiento es más costoso.
+ **Ligeros:** solo representan la interfaz. Son muy fáciles de mantener, pero se intercambia mucha información con el servidor.
$\space$
## 2.Diagramas
Veremos el diagrama de contexto y de contenedores.
$\space$
### 2.1.Diagrama de contexto

![[clie-server distr contexto.png]]
$\space$
### 2.2.Diagrama de contenedores

![[cli-server dsitr contenedor.png]]
$\space$
## 3.Características
Se usa cuando se quiere aumentar la robustez, escalabilidad y rendimiento del cliente-servidor clásico. Tiene las mismas ventajas que el cliente-servidor clásico, pero permite duplicar los servicios en otros servidores, por lo que aunque falle un servidor, el servicio sigue disponible. 

El problema es que si los servidores intermedios no son lo suficientemente eficientes a la hora de balancear la carga, el rendimiento se puede ver muy afectado. Es complicado determinar el rendimiento global.