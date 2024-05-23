[[Tema 2-Arquitecturas de división de responsabilidades]]
$\space$
## 1.Qué es la arquitectura en capas?
La arquitectura en capas se basa en separar las responsabilidades en capas, de forma que cada capa solo recibe peticiones de la capa anterior y solo las envía a la siguiente.
$\space$
### 1.1.Ventajas e inconvenientes
En la arquitectura en capas:
+ [p] Si se cambia una capa solo se afecta a las siguientes.
+ [c] Puede ser muy forzado organizar responsabilidades a veces en capas.
+ [c] No tiene buen rendimiento.
$\space$
## 2.Diagramas
Veremos el diagrama de contexto y de contenedores.
$\space$
### 2.1.Diagrama de contexto

![[capas contexto.png]]
$\space$
### 2.2.Diagrama de contenedores

![[contenedores capas.png]]
$\space$
## 3.Características
La arquitectura en capas solamente envía servicios a la capa inmediatamente superior. Siempre y cuando se mantengan las interfaces se puede modificar completamente una capa. Además permite implementar mecanismos de seguridad en cada capa, aumentando la fiabilidad del sistema. Favorece la portabilidad y el soporte multi-plataforma.

Se usa cuando se construyen sistemas empleando sistemas ya existentes, cuando hay que dividir las responsabilidades entre varios equipos de desarrollo o cuando son necesarios varios niveles de seguridad. 

El problema de esta arquitectura es es difícil a veces definir las responsabilidades de forma que toda petición atraviese todas las capas para ser procesada y para ser devuelta. Esto afecta mucho al rendimiento, pero es obligatorio para no romper la arquitectura.