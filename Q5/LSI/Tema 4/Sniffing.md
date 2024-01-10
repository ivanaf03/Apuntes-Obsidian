[[Tema 4-Sniffing]]

## ¿Qué es el sniffing?
Es una técnica que se utiliza en el campo de la seguridad informática para interceptar y capturar el tráfico de datos en una red de computadoras. El objetivo principal del "sniffing" es analizar y recopilar información de las comunicaciones que pasan a través de una red, lo que puede incluir datos confidenciales, contraseñas, mensajes de correo electrónico, archivos y otros tipos de información. 

Se puede esnifar paquetería de protocolos seguros o no seguros. Cuando se esnifan protocolos no seguros se obtiene toda la información en los payloads. Pero cuando se hace en un protocolo no seguro se obtiene información encriptada. Una autenticación basic en un servidor web no sirve de nada, está encriptado en base 64. Se descifra muy fácil con:
```
echo <password> | base64 -d 
```

### Analizadores
Los analizadores son programas, dispositivos o herramientas que se utilizan para examinar y procesar datos, ya sea para obtener información específica, diagnosticar problemas, realizar un seguimiento de actividades, realizar tareas de seguridad o para diversos fines de análisis.

## Sniffing en medio compartido
Un dominio de colisión es un conjunto de dispositivos que comparten un medio físico de transmisión y que, por lo tanto, compiten por él.

Legacy ethernet es una implementación antigua de ethernet basada en cable coaxial y protocolo de acceso al medio CSMA / CD. Cuando un equipo envía una trama, ésta llega a todos los equipos. Solo tiene 1 dominio de colisión. Utiliza hubs para conectar redes, pero sigue formando 1 solo dominio de colisión, por lo que todos los equipos reciben todo el tráfico.

Una NIC puede estar en modo:
+ **Normal:** sólo deja pasar el tráfico dirigido a su dir. MAC, bcast o mcast.
+ **Promiscuo:** acepta todos los paquetes.

## Sniffing en medio conmutado
El ethernet conmutado utiliza switches y bridges. Trabajan en capa 2, tomando decisiones sobre el envío de tramas en base a direcciones MAC. Reenvían tráfico sólo por el puerto en el que está conectada la máquina de destino. Cada equipo sólo recibe tráfico dirigido a él.

Tiene varios dominios de colisión, uno por puerto. Solo tiene un dominio de difusión o broadcast.

Para segmentar un dominio de difusión podemos:
+ Usar routers.
+ Crear VLANs.

Para capturar tráfico en un medio conmutado se utilizan las siguientes técnicas:
![[sniffing.png]]

### Port mirroring
Es una técnica utilizada en redes informáticas para la copia selectiva y redirección del tráfico de red desde un puerto de un switch de red a otro puerto, generalmente con fines de monitoreo y análisis.

### VLANs
Una VLAN es una agrupación lógica de dispositivos que se basa en la configuración de switches. Se pueden crear en un switch diferentes dominios de difusión, asignando cada puerto del switch a una agrupación VLAN concreta.

Se busca el rendimiento y el ahorro de direcciones. Antes en cada router había una clase C. El ancho de banda se dividía entre todas las máquinas. No sería muy óptimo si por ejemplo se dividen 10 Mbps de ancho de banda entre 200 máquinas.

Los puertos que están asignados a una única VLAN, se conocen como puertos de acceso. Los trunk ports son puertos que se utiliza para transportar datos de múltiples VLAN a través de un único cable o enlace de red. Las tramas se etiquetan antes de ser transmitidas por el enlace troncal.

Wi-Fi sigue teniendo problemas de rendimiento por el medio compartido a día de hoy.

Se utilizan lo siguientes protocolos en VLAN:
+ **DTP (Dynamic Trunking Protocol):** Permite a los switches acordar dinámicamente si un enlace debe ser un enlace troncal o no.
+ **802.1Q:** Se ataca con switch spoofing, es una técnica en la que un atacante finge ser un dispositivo legítimo en una red al falsificar su dirección MAC. Para protegerse basta con evitar que entren en los puertos tramas 802.1Q. Otro ataque es el double tagging, donde un atacante crea paquetes de red que tienen dos etiquetas VLAN en lugar de una sola. Esto puede confundir a los dispositivos de red y permitir que el tráfico evite las restricciones de seguridad impuestas por la segmentación de VLAN. La principal herramienta que se usa es Yersinia. También permite atacar DHCP, 802.1X, DTP, etc.
+ **STP(Spanning Tree Protocol):** Se utiliza para evitar bucles. Un paquete en bucle consumiría mucho ancho de banda. Este protocolo consiste en en transformar la estructura de VLAN en una estructura en árbol. Las tramas que utiliza son BPDU (Bridge Protocol Data Units). Al hacer un ataque convertimos nuestra máquina en root bridge, todo el tráfico pasaría por la máquina. También se puede hacer MITM.

Para protegernos podemos hacer:
+ **Root bridge guard:** Cuando está habilitado, el "Root Bridge Guard" supervisa los puertos en un switch para asegurarse de que no haya un intento de usurpar la posición del "puente raíz". Si se detecta que un puerto intenta convertirse en el "puente raíz" (a menudo debido a un error de configuración o un intento malicioso), el "Root Bridge Guard" desactivará automáticamente ese puerto para prevenir posibles problemas en la red.
  + **BPDU guard:** filtra los puertos para que no abran BPDU.

Para probar todo esto podemos usar GNS3, una herramienta similar a packet tracer. Es una herramienta de simulación de redes, pero permite darle una ISO a cada host.

## WIFI
Wi-Fi añade el modo monitor, que permite a la NIC capturar paquetes sin asociarse con el punto de acceso. Para sniffing podemos usar herramientas como tcpdump, wireshark, ettercap, bettercap, MITMF, n grep... Por ejemplo:
```
ngrep -d ens33 -q -W byline 'HTTP'
```

El protocolo WEP (Wired Equivalent Privacy) se basa en clave única y estática. El equipo necesita la clave para autenticarse ante el punto de acceso. La comunicación se cifra con la clave WEP y un IV (Vector de Inicialización). Al enviar la trama se envía este vector para que, conocida la WEP, se pueda descifrar. Utiliza RC4 como cifrado. Los problemas de este estándar es que IV es demasiado pequeño, solo 24 bits, y que RC4 es fácil de romper.

WPA (Wi-Fi Protected Access) utiliza claves dinámicas y corrige los problemas con RC4 de WEP. WPA2 utiliza AES-CCMP como algoritmos de cifrado. Aunque mejor
o mucho la seguridad, aparecieron nuevas debilidades, como krack attack y WPS.

### WPS
Wi-Fi Protected Setup es un estándar de seguridad de red presente en algunos routers que nos permite conectarnos de forma inalámbrica con tan solo pulsar un botón. Proporciona un pin de 8 dígitos a los dispositivos que no tengan WPS.

Es muy fácil de atacar. Se averiguó que simplemente con 4 primeros dígitos también se obtiene respuesta. Si el PIN es erróneo, el router nos lo dice. No hay mecanismo para limitar el número de intentos. Se puede atacar con herramientas como reaver.

### Krack Attack
Permite atacar al tráfico en una conexión wifi. Se basa en bloquear el mensaje 4 del handshaking para hacer que el cliente reinstale la contraseña. Se hace con un MITM.

WPA3 es el último estándar de wifi. Salió para evitar estos ataques, en 2018. Cambia la forma de realizar el handshake. Utiliza un nuevo proceso de handshake llamado "Simultaneous Authentication of Equals" (SAE). También cambia la longitud clave de cifrado, cifra las tramas de gestión. Existen nuevos ataques como Dragonblood contra WPA3.

### Sidejacking y cookies
Consiste en el robo de cookies de autenticación mediante xss, sniffing, etc. Con esas cookies puedo desde mi navegador acceder a la plataforma como otra persona. Las cookies se utilizan para autenticación, traceado (comunicación usuario-portal servidor), perfilado... Una cookie no es más que una string codificada con la fecha, datos de accesibilidad de la cookie, el protocolo, etc. 

En HTML5 se dejan de usar tanto las cookies y se empieza a usar el webstorage.

Las cookies pueden ser:
+ Supercookies
+ Cookies persistentes (se pueden implementar con el framework evercookie mediante envíos de HSTS)
+ Zombie cookies

### Robar tráfico en HTTPS
Una forma es con inyección en el certificado. Se puede hacer con sslstrip o sslstrip2, que intentan saltarse HSTS. Las máquinas no deben estar haciendo routing, ip forwarding, DHCP, etc.

## Herramientas de detección
+ **NEDEP:** Realiza petición ARP para cada IP a diagnosticar pero en lugar de dirigirla a la dirección de broadcast (FF:FF:FF:FF:FF:FF) lo hace a una aleatoria e inexistente. Sólo las interfaces en modo promiscuo aceptarán estos paquetes (aceptan todos), luego sólo estas interfaces contestarán a estas peticiones.
+ **Nast:** Busca tarjetas en modo "promiscuo“. Con = all comprueba todas las NIC de la red.
+ **Otras:** Sentinel, AntiSniff, SniffDet... 
