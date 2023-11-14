[[Tema 4-Sniffing]]

Libro: Lan switch security. What hacks know about your switch

### Sniffing
Es una técnica que se utiliza en el campo de la seguridad informática para interceptar y capturar el tráfico de datos en una red de computadoras. El objetivo principal del "sniffing" es analizar y recopilar información de las comunicaciones que pasan a través de una red, lo que puede incluir datos confidenciales, contraseñas, mensajes de correo electrónico, archivos y otros tipos de información. 

Se puede esnifar paquetería de protocolos seguros o no seguros. Cuando se esnifan protocolos no seguros se obtiene toda la información en los payloads. Pero cuando se hace en un protocolo no seguro se obtiene información encriptada. Una autenticación basic en un servidor web no sirve de nada, está encriptado en abse 64. Se descrifra muy fácil con echo "password" | base64 -d. 

##### Analizadores
Los analizadores son programas, dispositivos o herramientas que se utilizan para examinar y procesar datos, ya sea para obtener información específica, diagnosticar problemas, realizar un seguimiento de actividades, realizar tareas de seguridad o para diversos fines de análisis.

##### Port mirroring
Es una técnica utilizada en redes informáticas para la copia selectiva y redirección del tráfico de red desde un puerto de un switch de red a otro puerto, generalmente con fines de monitoreo y análisis.

### Subneting
Se buscaba el rendimiento y el ahorro de direcciones. Antes en cada router había una clase C. El ancho de banda se dividía entre todas las máquinas. No sería muy óptimo si por ejemplo se dividen 10 Mbps de ancho de banda entre 200 máquinas.

Una VLAN es una técnica de segmentación de redes que permite dividir una red física en múltiples redes lógicas separadas, aisladas y virtuales. Cada VLAN funciona como si fuera una red local independiente, a pesar de compartir la misma infraestructura física. Esto permite formar una subred entre conmutadores situados en diferentes ubicaciones geográficas. 

Los trunk ports son puertos que se utiliza para transportar datos de múltiples VLAN a través de un único cable o enlace de red.

Wi-Fi sigue tieniendo problemas de rendiemiento por el medio compartido a día de hoy.

##### Protocolos
+ **DTP** 
+ **802.1Q:** Se ataca con switch spoofing, es una técnica en la que un atacante finge ser un dispositivo legítimo en una red al falsificar su dirección MAC. Para protegerse basta con evitar que entren en los puertos tramas 802.1Q. Otro ataque es el double tagging, donde un atacante crea paquetes de red que tienen dos etiquetas VLAN en lugar de una sola. Esto puede confundir a los dispositivos de red y permitir que el tráfico evite las restricciones de seguridad impuestas por la segmentación de VLAN. La principal herramienta que se usa es Yersinia. También permite atacar DHCP, 802.1X, DTP, etc.
+ **STP:** Se utiliza para evitar bucles. Un paquete en bucle consumiría mucho ancho de banda. Este protocolo consiste en en transformar la estructura de VLAN en una estructura en árbol. Las tramas que utiliza son BPDU. Al hacer un ataque convertimos nuestra máquina en root bridge, todo el tráfico pasaría por la máquina. También se puede hacer MITM.

##### Medidas de protección
+ **Root bridge guard:** Cuando está habilitado, el "Root Bridge Guard" supervisa los puertos en un switch para asegurarse de que no haya un intento de usurpar la posición del "puente raíz". Si se detecta que un puerto intenta convertirse en el "puente raíz" (a menudo debido a un error de configuración o un intento malicioso), el "Root Bridge Guard" desactivará automáticamente ese puerto para prevenir posibles problemas en la red.
  + **BPDU guard:** filtra los puertos para que no abran BPDU

GNS3 es una herramienta similar a tacket tracer. Es una herramienta de simulación de redes, pero permite darle una ISO a cada host.


