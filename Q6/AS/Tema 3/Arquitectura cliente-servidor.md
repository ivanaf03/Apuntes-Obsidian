[[Tema 3-Arquitecturas centradas en la independencia de componentes]]
$\space$
## 1.Qué es la arquitectura cliente-servidor?
El cliente-servidor es una arquitectura basada en la organización de funcionalidades como servicios independientes proporcionados por componentes específicos. También se conoce como arquitectura orientada a servicios. Los clientes interactúan con el servidor, los servicios son transparentes para ellos.
$\space$
### 1.1.Ventajas e inconvenientes
La arquitectura cliente-servidor:
+ [p] Es muy robusta, si falla un servicio no afecta en nada el resto.
+ [c] El servidor es un punto único de fallo y limita el rendimiento.
$\space$
## ## 2.Diagramas
Veremos el diagrama de contexto y de contenedores.
$\space$
### 2.1.Diagrama de contexto

![[contexto cliente server.png]]
$\space$
### 2.2.Diagrama de contenedores

![[contenedor cliente server.png]]
$\space$
## 3.Características
Se suele usar esta arquitectura en sistemas incrementales, ya que no todos los servicios tienen que estar acabados para que el sistema funcione. A veces es buena solución cuando no encajan otras arquitecturas.

Los servicios, al ser independientes, pueden duplicarse si hay una muy alta demanda de alguno de ellos. Permite ofertar solo ciertos servicios a ciertos clientes, por ejemplo usando roles.

Sin embargo, el servidor tiene que balancear la carga y funcionar como directorio, por tanto es un único punto de fallo y limita el rendimiento. Es muy difícil saber el rendimiento global que habrá, ya que depende de la carga de cada servicio.