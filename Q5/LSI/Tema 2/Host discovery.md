[[Tema 2-Information gathering]]

## ¿Qué es el host discovery?
El host discovery consiste en identificar y encontrar dispositivos o hosts activos en una red. Sirve como primer paso para el port scanning, ya que hacerlo sobre todas las IPs de un rango podría ser un proceso muy costoso. También se llama escaneo ping o descubrimiento de sistemas. Se pueden utilizar herramientas como nmap, hping3, scapy, etc.

## Comando nmap
A pesar de que su función principal es el port scanning, nmap permite realizar host discovery. Sin flags nmap realiza un escaneo de host y puertos en todas las máquinas de una red:
```
nmap x.x.x.x
```

### Opciones de nmap
+ **--packet-trace:** permite ver los paquetes que envía nmap
+ **-sL:** lista los equipos de la red especificada, sin enviar paquetes. Utiliza resolución DNS inversa para obtener sus nombres.
+ **-sP:** hace host discovery enviando paquetes a los objetivos (ICMP echo request, TCP SYN al puerto 443, TCP ACK al puerto 80, ICMP timestamp). En el caso de que el usuario que realiza el escaneo no tenga privilegios suficientes para enviar paquetes SYN (paquetes de inicio de conexión) a los puertos 80 y 443 utilizando una llamada al sistema "connect()", se limitará a enviar paquetes SYN a estos puertos. 
+ **-PR:** envia solicitudes ARP a los hosts de la red y espera respuestas para determinar si los hosts están vivos o no. 
+ **--send-ip:** permite evitar que Nmap utilice ARP y, en su lugar, enviará solicitudes IP para descubrir sistemas en la red. El algoritmo que usa nmap para procesar las solicitudes ARP es mucho más rápido y fiable que los escaneos basados en IP.
+ **-PE:** realiza un escaneo de descubrimiento de hosts utilizando paquetes ICMP Echo Request.
+ **-PS:** realizar un escaneo de descubrimiento de hosts enviando paquetes TCP SYN a un puerto específico en los hosts de la red. Por defecto hace PS80, pero también se le puede indicar una lista de puertos. Por ejemplo: PS22,23,25,80... No importa si el puerto está abierto o cerrado, es decir, da igual que llegue un SYN/ACK ou un RST, si llega respuesta sabemos que la máquina está viva. Funciona contra firewall con control de estado.
+ **-PA:** realiza un escaneo de descubrimiento de hosts utilizando paquetes TCP ACK. Este tipo de escaneo se utiliza para determinar si un host está activo en la red, pero no verifica si un puerto específico está abierto o cerrado en el host. En lugar de intentar establecer una conexión TCP completa, el escaneo ACK simplemente envía paquetes TCP ACK y espera respuestas. Si el usuario no tiene privilegios para llamar a "connect()" envía SYN. Se especifica una lista de puertos al igual que -PS. Funciona contra sin control de estado.
+ **-PU:** envía un paquete UDP vacio al puerto 40125 por defecto. Se envía a puertos que suelen estar cerrados porque UDP no confirma respuesta; pero sí se devuelve un ICMP de puerto no alcanzado si la máquina está viva. Es útil porque hay firewall que solo filtran TCP.
+ **-PP:** se utiliza para forzar a nmap a enviar un paquete de echo ICMP (ping) a través del protocolo ICMP a la máquina de destino, independientemente de otras configuraciones. Es útil para determinar si un host remoto está activo y responde a paquetes ICMP. Si se recibe una respuesta ICMP, nmap considera el host como activo.
+ **-PM:** se utiliza para forzar a nmap a enviar un paquete de echo ICMP (ping) a través del protocolo ICMP, pero con la adición de paquetes UDP y paquetes TCP SYN en el puerto 80 al host de destino. Esta opción puede ser útil para determinar si un host está vivo y también puede indicar si un host tiene un firewall o filtrado de paquetes que afecta a los protocolos UDP o TCP.
+ **-PN:** se utiliza para tratar a todos los hosts de la red como si estuvieran vivos. No es compatible con -sP.
+ **-n:** evita la resolución DNS inversa y ahorra tiempo.
+ **-R:** realiza resolución de nombres a todos los objetivos.
+ **--dns-servers:** define que servers utilizar para las consultas DNS.

### Salidas de nmap
+ **-oN:** guarda la salida en un formato normal de texto plano.
+ **-OG:** produce una salida que es fácil de analizar con herramientas como grep.
+ **-oX:** guarda la salida en formato XML.

## Firewalls
Un firewall es un sistema o dispositivo diseñado para proteger una red o un sistema informático al controlar y filtrar el tráfico de red que entra y sale. Su función principal es actuar como una barrera entre una red interna y redes no confiables, como Internet, para prevenir o mitigar amenazas y ataques cibernéticos. Los firewalls pueden ser tanto software como hardware, y a menudo se utilizan en combinación para proporcionar una defensa en capas.

### Tipos de firewall
+ **Sin control de estado:** suele trabajar en capas 3 y 4 y decide que deja o no deja conectarse, filtrando el tráfico. Cada paquete se evalúa de forma independiente y no se considera la relación con otros paquetes. Toman decisiones basadas únicamente en las reglas definidas.
+ **Con control de estado:** mantienen una tabla de estado en la que registran información sobre las conexiones, como las direcciones IP origen y destino, los puertos, el estado de la conexión, por ejemplo, establecida, en curso, cerrada... Hace lo mismo que el firewall sin control de estado, pero verificando que se sigue el handshaking de apertura y cierre (envío de SYN, recepción de ACK+SYN...). Para escanear un firewall de este tipo tenemos que usar el flag SYN.