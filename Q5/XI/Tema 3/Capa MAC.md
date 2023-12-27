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
Este protocolo:
+ Utiliza CSMA/CA (para broadcast).
+ Utiliza CSMA/CA + ACK (para unicast).
+ Espera exponencial binaria para control de congestión (CW se dobla en cada intento de retransmisión (CWmin = 15, CWmax = 1023) y se resetea a CWmin después de una transmisión exitosa).
+ RTS/CTS opcional para ayudar a evitar el problema del nodo oculto.
+ CS se lleva a cabo física y virtualmente (mediante el NAV (Network Allocation Vector)).

La priorización de tramas se basa en:
+ **SIFS:** para ACK y CTS.
+ **PIFS**
+ **DIFS:** data y RTS.

![[difs 1.png]]
### Ejercicio 1
![[difs 2.png]]

### Ejercicio 2
![[difs 3.png]]

### DCF con RTS/CTS
NAV es un contador descendente que se establece cuando una estación transmite un paquete y quiere reservar el medio para una secuencia de transmisión continua. El NAV indica a otras estaciones la duración estimada de tiempo durante la cual el medio estará ocupado.

Antes de que una estación transmita datos, puede enviar un paquete RTS a la estación receptora. El paquete RTS indica la intención de transmitir y solicita permiso para hacerlo.

La estación receptora responde con un paquete CTS, indicando que está lista para recibir la transmisión. Estos paquetes también contienen el campo Duration, que especifica la duración estimada de la transmisión.
![[Imágenes/nav.png]]
Utiliza espaciados SIFS para reservar el medio:
![[nav 1.png]]
Las colisiones solo ocurren ahora en la transmisión de RTS. En caso de que el tamaño de las tramas se deba reducir, podemos fragmentarlas. Los fragmentos se envían seguidos usando SIFS. Cada fragmento y ACK también lleva asociado un NAV menos el último.
![[nav 2.png]]


## IEEE 802.11e
IEEE 802.11e es una extensión del estándar IEEE 802.11, que especifica mejoras en el rendimiento y la calidad de servicio (QoS) para redes inalámbricas. Este estándar fue desarrollado para abordar las limitaciones en términos de capacidad y eficiencia del estándar original IEEE 802.11.

Introduce mejoras MAC para mejorar el QoS. Además usa HCF (Hybrid Coordination Function) en lugar de PCF y DCF, pero es retrocompatible.

El Transmission Opportunity (TXOP) es un protocolo donde un nodo puede apropiarse del canal (sin tener que competir por él) durante un intervalo de tiempo para transmitir una ráfaga de datos. También usa block ACK, que permite usar un solo ACK para varias tramas consecutivas.

### IEEE 802.11e EDCF 
802.11e EDCF (Enhanced Distributed Channel Access) se refiere a una mejora específica en el mecanismo de acceso al canal en redes inalámbricas según el estándar IEEE 802.11e. Este estándar se enfoca en mejorar la calidad de servicio (QoS) en redes Wi-Fi.

Utiliza espaciado AIFS (Arbitration InterFrame Space), que es más corto para paquetes de mayor prioridad. Por defecto, de mayor a menor prioridad:
+ Voz
+ Vídeo
+ Best effort
+ Background

### Ejercicio EDCF
![[ejercicio edcf.png]]