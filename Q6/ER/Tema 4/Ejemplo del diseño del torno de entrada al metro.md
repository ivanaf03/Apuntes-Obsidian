[[Tema 4-Diagramas de clases en ingeniería de requisitos]]
$\space$
## 1.Descripción
El objetivo es cobrar 1 euro a cualquier usuario que entre al metro. No se puede entrar sin pagar. Cualquiera que introduzca 1 euro puede pasar.

Para solucionar los posibles problemas hay un guardia en la puerta cobrando la entrada. Si alguien intenta colarse lo detiene. Se tiene que crear el software para el sistema de entrada de torno usado.
$\space$
### 1.1.Sistema y entorno
El sistema y el entorno actúan a través de los eventos compartidos.

El entorno controla que se meten monedas en la ranura. El sistema detecta la moneda y desbloquea la barrera. El entorno detecta que la barrera está desbloqueada y el usuario puede entrar. El sistema detecta que la barrera está girando y pasado un tiempo la bloquea.
$\space$
### 1.2.Requisitos
Los requisitos son:
+ Cuando un usuario mete una moneda, se desbloquea el torno.
+ El usuario puede pasar cuando el torno está desbloqueado.
+ Si el torno está bloqueado mucho tiempo, se bloquea automáticamente.
+ Cuando el torno haya girado un tercio se bloquea de nuevo.
$\space$
## 2.Entidades
En el entorno tenemos al viajero, las monedas y el torno. En la interfaz tenemos la ranura de monedas y la barrera. Por último, en el sistema tenemos el propio software.

![[ejemplo torno.png]]






