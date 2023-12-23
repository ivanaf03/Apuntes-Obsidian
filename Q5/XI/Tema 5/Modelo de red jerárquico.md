[[Tema 5-Cableado estructurado]]

## Modelo en 3 capas
Los modelos de diseño de red ayudan a diseñar redes corporativas. El modelo de 3 capas se divide en:
+ **Núcleo:** transporte entre las redes de los edificios de un campus.
+ **Distribución:** políticas de red, filtrado de tráfico y enrutamiento eficiente.
+ **Acceso:** acceso físico a la red para los usuarios finales y sus dispositivos.

Se basa en un modelo jerárquico, donde cada capa se encarga de cumplir una serie de tareas. Intenta determinar los dispositivos adecuados que se usan en cada capa y las funcionalidades que se deben implementar en cada dispositivo. No es necesario que las funciones se implementen en dispositivos diferentes.

### Capa de acceso
Proporciona al usuario final acceso a la red. Está formada por switches de capa 2. Gracias a esto se cada host final tiene ancho de banda completo. Además se segmenta la red.

Sus funcionalidades son:
+ Conmutación de capa 2
+ Conexiones redundantes con la capa de distribución.
+ Seguridad de puerto.
+ Spanning Tree, un protocolo utilizado para evitar bucles de red en topologías con conexiones redundantes. 
+ PoE (Power over Ethernet), transmisión de datos y energía eléctrica a través del mismo cable de red.

### Capa de distribución
Centraliza la conectividad de red en un edificio. Aísla el núcleo de la capa de acceso.

Sus funcionalidades son:
+ Balanceo de carga y redundancia de enlaces.
+ Agregación de conexiones.
+ Definición de dominios de broadcast (VLANs).
+ Conectividad basada en políticas, con las que se define la conectividad entre grupos de dispositivos (ACLs).
+ Enrutamiento entre VLANs (Switch multicapa).

### Capa núcleo
Es la parte central de la red, cuya principal función es conmutar paquetes de datos a alta velocidad.

Sus funcionalidades son:
+ Proporcionar alta velocidad y baja latencia.
+ No realizar manipulación de paquetes que requiera un alto consumo de CPU.
+ Mantener alta disponibilidad y tolerancia a fallos.

## Red corporativa
La arquitectura de red corporativa es un modelo que facilita el diseño de redes de tamaño muy grande, que necesitan una alta escalabilidad. Se usa en entornos muy sofisticados, para los no es suficiente el modelo jerárquico de 3 capas.

Se basa en una estructura modular:
+ **Área de campus:** capas de acceso, distribución y data center.
+ **Área de frontera corporativa:** acceso a internet, comunicaciones WAN y VPN.
+ **Área de proveedor de servicios:** proveedores de internet y de servicios WAN, telefonía.
+ **Área de acceso remoto:** sucursales, teletrabajo, cloud.
