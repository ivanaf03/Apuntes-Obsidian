[[Tema 3-IEEE 802.11]]

## Problemas de acceso al medio
En medios cableados se puede usar CSMA/CD, que consiste en enviar tan pronto esté el nodo libre, escuchando al medio para saber si hubo colisiones. Pero en medios inalámbricos no funciona:
+ **Problema del nodo oculto:** Mientras A está enviando datos a B, C puede no ser consciente de esta transmisión y, por lo tanto, no puede recibir datos de A. Esto se debe a que C no está en el rango de detección de la señal de A. Cuando C decide enviar datos a B, realiza un chequeo de portadora (Carrier Sense, CS) y determina que el medio está "libre" porque no puede detectar la transmisión de A a B. Sin embargo, en realidad, el medio no está libre porque A está transmitiendo a B. Supongamos que C decide enviar datos a B al mismo tiempo que A está transmitiendo a B. Esto puede resultar en una colisión en el nodo B. Sin embargo, A puede no ser consciente de la colisión porque no puede escuchar directamente a C. Esto implica que el mecanismo de Detección de Colisiones (Collision Detection, CD) falla. En este contexto, A está "oculto" para C y viceversa porque ambos nodos no pueden detectar directamente la actividad del otro.
+ **Problema del nodo expuesto:** Mientras B está enviando datos a A, C quiere enviar datos a otro nodo que no es ni A ni B. C realiza una detección de portadora (Carrier Sense) y detecta que el medio está en uso debido a la transmisión de B a A. Como resultado, C decide esperar antes de intentar enviar sus datos. La complicación surge porque, aunque C detecta que el medio está ocupado debido a la transmisión de B a A, la transmisión de B a A no afecta directamente la capacidad de C para comunicarse con un nodo que no es A ni B. En este caso, esperar es innecesario, ya que la actividad de B no afecta la comunicación planificada de C con otro terminal. El término "expuesto" se refiere a la situación en la que un nodo, en este caso, C, está en el rango de detección de actividad de otro nodo, B, aunque la transmisión de B no tenga un impacto directo en la comunicación planificada de C.

### Problemas de acceso al medio en conexiones inalámbricas
+ La potencia de señal disminuye con el cuadrado de la distancia.
+ El emisor podría aplicar CS y CD, pero las colisiones ocurren en el receptor.
+ Con radios half-duplex, CD no es posible.

## CSMA/CA
Consiste en usar Collision Avoidance (CA) en lugar de Collision Detection (CD). 
+ Si el canal está libre transmitir sin esperar.
+ Si el canal está ocupado esperar hasta que esté libre y entonces esperar (back off) un número aleatorio de slots en el intervalo (0, Contention Window).

El tiempo invertido en la cuenta atrás se considera parte del overhead (gasto adicional) del protocolo de control de acceso al medio (MAC), ya que es un tiempo en el que el canal no se utiliza para la transmisión de datos. Un CW muy grande aumenta el tiempo de espera y un CW pequeño el número de colisiones.

### MACA
Multiple Access with Collision Avoidance utiliza paquetes de señalización para evitar las colisiones:
+ **RTS (Request To Send):** El emisor solicita al receptor el derecho a transmitir un paquete de datos mediante la transmisión de un pequeño paquete RTS antes de transmitir dicho paquete de datos.
+ **CTS (Clear To Send):** El receptor concede el derecho a que el transmisor envíe su paquete.

MACA soluciona los problemas de nodo expuesto y nodo oculto.

## IEEE 802.11 DCF
