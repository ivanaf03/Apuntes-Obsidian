[[Tema 3-Arquitecturas centradas en la independencia de componentes]]
$\space$
## 1.Qué es la arquitectura líder-trabajador?
Esta arquitectura se basa en un elemento que actúa como líder recibiendo y asignando peticiones al resto de elementos, los trabajadores, a los cuales gestiona y coordina. 
$\space$
### 1.1.Ventajas e inconvenientes
La arquitectura líder-trabajador:
+ [p] Separa muy claramente las tareas de gestión de las funcionalidades, lo que mejora el rendimiento y la escalabilidad.
+ [c] Es difícil prevenir la carga de trabajo.
$\space$
## 2.Diagramas
Veremos el diagrama de contexto y de contenedores.
$\space$
### 2.1.Diagrama de contexto

![[contexto cliente distr.png]]
$\space$
### 2.2.Diagrama de contenedores

![[cliente distr contenedor.png]]
$\space$
## 3.Características
Esta arquitectura se usa cuando se necesitan tiempos de respuesta eficientes y flexibilidad en cuanto a la carga que recibe el sistema. Crear y parar trabajadores permite optimizar el uso de recursos en función de la demanda del sistema. 

El problema es que el líder es un punto único de fallo. Debe someterse constantemente a pruebas para no comprometer a la disponibilidad del sistema.