[[Tema 6-Redes de almacenamiento]]

## Fiber Channel
La arquitectura de Fibre Channel es un conjunto de especificaciones que definen cómo se realiza la comunicación de datos en una red de almacenamiento. Soporta operaciones en modo bloque con direccionamiento de 24 bits. Está disponible en diferentes velocidades de transferencia, como 1, 2, 4, 8, 16, 32, 64 y 128 Gb.

Se basa en un modelo de referencia de cinco niveles:
- **FC0 (FCO - Fiber Channel Physical Interface):** Capa de interfaz física que especifica los tipos de cableado y características de los conectores.
- **FC1 (Fiber Channel Transmission Protocol):** Capa de protocolo de transmisión o enlace de datos, donde se definen los mecanismos de codificación y acceso al medio.
- **FC2 (Fiber Channel Signaling Protocol):** Capa de protocolo de señalización o red, que se encarga de la conversión de bloques de códigos en tramas, la gestión de la calidad de servicio (QoS) y el control de flujo.
- **FC3 (Common Services Layer):** Capa de servicios comunes que incluye funciones como cifrado y compresión de datos.
- **FC4 (Protocol Mapping Layer):** Capa de mapeo de protocolos diferentes a Fiber Channel. Permite la interoperabilidad con diferentes protocolos de aplicación.

Los dispositivos de un entorno FC tienen un identificador único denominado World Wide Name (WWN) y cada uno de sus puertos una dirección de puerto de 24 bits. Estas direcciones se utilizan para implementar los algoritmos de balanceo, tolerancia a fallos y seguridad. 

Zoning es un mecanismo que permite segmentar los puertos del switch en grupos aislados. Permite controlar qué dispositivos pueden comunicarse entre sí, proporcionando una capa adicional de seguridad y organización en la red. Esto se hace para garantizar la integridad de los datos y también para facilitar la administración y el mantenimiento de la red. Puede ser:
- **Hardware:** Basado en los puertos físicos del switch.
- **Software:** Basado en direcciones lógicas asignadas a los dispositivos, como los WWN.

También permite trunking, un mecanismo que permite combinar varios puertos en un solo enlace lógico de mayor capacidad.

### Topologías
+ **FC-P2P (Punto a Punto):** conexión directa entre dos equipos (punto a punto). Cada par de dispositivos está conectado sin la necesidad de compartir el ancho de banda con otros dispositivos.
    - **Ventajas:** Permite superar problemas de distancia y conectividad, ya que la conexión es directa.
    - **Desventajas:** Puede volverse complicado y costoso cuando se tienen muchos dispositivos que necesitan conectarse entre sí.
+ **FC-AL (Anillo Arbitrario o Loop):** los dispositivos están conectados en un bucle o anillo. Cada dispositivo en el anillo está conectado al siguiente y al anterior, formando un circuito cerrado. Todos los dispositivos comparten el ancho de banda disponible en el anillo. Sin embargo, un fallo en un dispositivo puede interrumpir toda la comunicación en el conjunto.
    - **Ventajas:** Es una topología simple y fácil de implementar.
    - **Desventajas:** Un fallo en un dispositivo puede afectar a la comunicación en toda la red, y el ancho de banda se comparte entre todos los dispositivos en el bucle.
+  **FC-SW (Conmutada o Fabric):** los dispositivos Fibre Channel están interconectados mediante conmutadores (switches). Cada dispositivo se conecta directamente al switch, y el switch gestiona las conexiones entre ellos. Teóricamente, cada dispositivo puede trabajar al máximo ancho de banda disponible, ya que el switch crea enlaces dedicados para cada conexión abierta.
    - **Ventajas:** Permite una alta escalabilidad, eficiencia y flexibilidad en la gestión de la red. Los fallos en un dispositivo no afectan a los demás.
    - **Desventajas:** Puede ser más costoso y complejo en comparación con otras topologías.

### FC over Ethernet
FCoE es una tecnología que permite la transmisión del protocolo Fibre Channel sobre redes Ethernet, específicamente en velocidades de 10 Gigabits por segundo (10Gb) hasta 200 Gigabits por segundo (200Gb). FCoE fue diseñado para proporcionar una convergencia de tecnologías de almacenamiento y redes en centros de datos, eliminando la necesidad de tener infraestructuras de red y almacenamiento por separado.

Sustituye las capas FC0 y FC1. Los servidores utilizan tarjetas convergentes, conocidas como Converged Network Adapters (CNA). Estas tarjetas combinan funcionalidades de Network Interface Cards (NIC) y Host Bus Adapters (HBA) en una sola tarjeta.

## SCSI
Small Computer System Interface es un conjunto de estándares que define cómo los ordenadores pueden comunicarse con periféricos y transferir datos a nivel de bloque. 

SCSI define cómo se lleva a cabo la transferencia de datos entre ordenadores y periféricos a nivel de bloques de datos. Involucra comandos, protocolos e interfaces físicos que permiten la comunicación eficiente entre los dispositivos.

Utiliza topología en forma de bus. En esta topología, hay un iniciador, Host Bus Adapter, que inicia la comunicación, una serie de dispositivos encadenados conocidos como targets, y un terminador de bus que garantiza la correcta terminación de la señal en el extremo del bus. El iniciador puede direccionar unidades lógicas en los dispositivos target, lo que permite el acceso a porciones específicas de bloques de datos, como sectores en un disco duro.

### iSCSI
Internet Small Computer System Interface es un protocolo de red que permite el uso del protocolo SCSI sobre redes IP. Permite a un host utilizar un iniciador para conectarse, a nivel de bloque, a un target. 

Es más barato que FC, pero rinde un poco peor por culpa del protocolo TCP/IP.

Facilita el "disaster recovery" a un costo razonable. Esto se debe a que permite la migración y sincronización de discos a través de redes WAN, lo que es beneficioso para la replicación de datos y la continuidad del negocio en escenarios de desastre.