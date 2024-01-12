[[Tema 5-DoS y monitorización]]

## ¿Qué es un ataque DoS?
Es un ataque caracterizado por un intento explícito de denegar a los usuarios legítimos el uso de un servicio o recurso. Los protocolos suelen estar diseñados para ofrecer servicios, no para prevenir o evitar estos ataques.

### Ataques lógicos
Aprovechan una vulnerabilidad del protocolo, aplicación o sistema. Son vulnerabilidades que se pueden parchear o se pueden definir reglas en los firewalls.

También se pueden dar por una mala configuración. Por ejemplo, si un usuario es tonto y ejecuta:
```
while true do fork()
```

La solución para esto es ponerle cuotas a los usuarios de uso de CPU, espacio en disco, memoria...

El PoD (Ping of Death) consiste en enviar un ping malformado a una computadora. Antes los sistemas operativos no podían soportar pings con excesos de bytes.

Otro ataque famoso es el teardrop. Consistía en enviar datos fragmentados, pero solapados entre ellos, por ejemplo, 1-1000, 500-1500... Los ordenadores crasheaban.

Los ataques LAND eran ataques basados en spoofing. Se envían paquetes SYN con IP origen la propia máquina objetivo. Se queda en bucle infinito.
```
hping3 -S 10.11.48.100 -a 10.11.48.100
```

### Ataques de inundación
Son ataques donde se abren muchísimas conexiones que hacen que el servicio vaya más lento o se caiga. Son los ataques que más problemas dan. Se pueden hacer con packit, scapy o hping3.

```
packit -b 0 -c 0 -sR -d 10.11.49.49 -F s -S 1000 -O 80

# Se puede jugar con la flag -S para que el firewall deje pasar las salidas a ese puerto
```

```
hping3 -S -p 80 --flood --rand-source 10.11.49.49
```

El factor de amplificación es el número de paquetes que le llegan a la máquina que queremos atacar. Por ejemplo, si 120 máquinas hacen un PING a otra máquina, ese "ataque" tiene un factor de amplificación de 120.

El TCP SYN flood es un ataque que intenta llenar la cola TCB abriendo muchísimas conexiones. Si esta se llena la máquina ya no aceptará más conexiones. Se puede modificar en /proc/sys/net/ipv4/tcp_max_back_log que está por defecto a 128. Este ataque se puede evitar con:
+ **SYN Cookies:** La idea de las SYN Cookies es aprovechar el número de secuencia para codificar datos. Se activan con  echo 1 > /proc/sys/net/ipv4/tcp_syncookies. Guardan la información mínima para abrir conexiones.
+ **SYN Cachés:** consisten en es usar una una estructura de datos independiente de la TCB, con un tamaño limitado y en la que se guarda sólo un subconjunto de datos de los que se guardarían normalmente en la TCB. Si se completa el handshake y se recibe el ACK, estos datos se copian a la TCB.
+ **SYN Proxies:** Evita que las máquinas en lugar de abrir conexiones contra la máquina las abra el syn proxy y hace el handshake. Cuando está hecha le pasa la conexión a la máquina. 

Otros ataques mucho más dañinos son los UDP flood porque simplemente se envían cosas a puertos UDP random, no se puede cortar tan fácil el handshake. Se pueden hacer con udpflood.

### Ataques directos
Consisten en envío masivo de paquetes de manera directa a la víctima con dirección origen falsificada.

Los ataques slowloris por defecto abren muchas conexiones con cabeceras sin retorno de línea. Esto ralentiza la conexión.

Un modo es el slow POST. Hace peticiones muy lentas y envía poco a poco las cosas para ralentizar las conexiones.

Otro modo es el slow READ. Hace algo de forma similar con peticiones GET.

Una herramienta de denegación de servicio https es thc hacker choice. Otra es Tor's hammer, que hace ataques POST pero a través de la red Tor. Ven las IP del exit node Tor.

### Ataques reflectivos
Son inundaciones con ip origen la máquina que quiero inundar e ip destino muchas otras máquinas. Se puede proteger con un firewall con control de estado. Como la máquina atacada no inicia el SYN, el firewall corta todas esas conexiones. Aunque parezca que no, el UDP si tiene control de estado en estos firewalls. Cuando se establece una conexión UDP el firewall lo marca y simula el control de estado.

El factor de amplificación es la relación entre las tramas recibidas por la víctima por cada trama transmitida por el atacante.

Dos ataques típicos son SMURF, con ICMP, y FRAGGLE, con UDP.

En un ataque de broadcast cuando a un router le llegan paquetes de broadcast foráneos debe dropearlos. Se pone en el fichero /proc/sys/netipv4/icmp-echo-ignore-broadcast 1 y el fichero icmp-echo-ignore-all 1. El fichero rep-filter 1 (o 2) verifica si el paquete es accesible desde esa interface de red.

## Denegación a una organización
El Spanning Tree Protocol es un protocolo utilizado en redes de área local (LAN) para evitar bucles en la topología de red. El STP selecciona caminos redundantes y bloquea algunos de ellos para garantizar una estructura de red sin bucles.

El tráfico se gestiona con QoS. Deja pasar con prioridad el tráfico legítimo, dropea el tráfico dudoso y deja pasar con menos prioridad el tráfico dudoso.

Si consigues configurar tu máquina como rootbridge puedes cargarte toda la organización.

El Traffic Shaping es una técnica que se utiliza para controlar el flujo de tráfico en una red. El Packet Shaping se enfoca en el control y la priorización del tráfico a nivel de paquetes. Están vinculados a QoS. Permiten aguantar mejor los ataques DDoS. 

También se suelen usar reverse proxys para ello. Funcionan de forma que para que las máquinas que entran a los servidores web de una organización desde internet tengan que pasar por ellos.


