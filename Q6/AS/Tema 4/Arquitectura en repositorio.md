[[Tema 4-Arquitecturas centradas en la comunicación]]
$\space$
## 1.Qué es la arquitectura en repositorio?
La arquitectura en repositorio se basa en el intercambio de información entre componentes a través de un repositorio central compartido al que todos acceden. Los componentes no interactúan entre ellos, solo con el repositorio.
$\space$
### 1.1.Ventajas e inconvenientes
La arquitectura en repositorio:
+ [p] Minimiza el número de envíos de información.
+ [c] El repositorio es el punto único de fallo.
$\space$
## 2.Diagramas
Veremos el diagrama de contexto y de contenedores.
$\space$
### 2.1.Diagrama de contexto

![[contexto repositorio 1.png]]
$\space$
### 2.2.Diagrama de contenedores

![[repositorio contenedor.png]]$\space$
## 3.Características
Esta arquitectura se usa en sistemas en los que es necesario intercambiar una gran cantidad de información o en los que la aparición de información en el repositorio. En este último caso los sistemas se llaman productores-consumidores.

La ventaja del sistema es que los componentes son totalmente independientes. Las políticas aplicadas a los datos solo se trabajan en el repositorio. Una vez se hacen cambios en la información, todos los componentes lo sabrán inmediatamente.

El problema es que el repositorio, el ser el único punto de fallo, puede dar problemas a la hora de hacer copias de seguridad. Además, la información del repositorio debe tener un formato válido para todos los componentes, evitando así pérdidas de rendimiento haciendo conversiones.