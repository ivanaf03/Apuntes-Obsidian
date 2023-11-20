[[Tema 5-DoS]]

### Ataques lógicos
Son vulnerabilidades que se pueden parchear. También se pueden dar por una mala configuración. Por ejemplo, si un usuario es tonto y ejecuta:
```
while true do fork()
```

La solución para esto es ponerle cuotas a los usuarios de uso de CPU, espacio en disco, memoria...

### Ataques de inundación
Son ataques donde se abren muchísimas conexiones que hacen que el servicio vaya más lento o se caiga. Son los ataques que más problemas dan.

El factor de amplificación es el número de paquetes que le llegan a la máquina que queremos atacar. Por ejemplo, si 120 máquinas hacen un PING a otra máquina, ese "ataque" tiene un factor de amplificación de 120.

##### Botnet
Una botnet es una red formada por cientos de máquinas infectadas. Se utilizan para hacer DDoS.

### Ataques directos
(P2)

### Ataques reflectivos
Son inundaciones con ip origen la máquina que quiero inundar e ip destino muchas otras máquinas. Se puede proteger con un firewall con control de estado. Como la máquina atacada no inicia el SYNC, el firewall corta todas esas conexiones. Aunque parezca que no, el UDP si tiene control de estado en estos firewalls. Cuando se establece una conexión UDP el firewall lo marca y simula el control de estado.

##### Ejemplos
+ Ataque de broadcast. Cuando a un router le llegan paquetes de broadcast foráneos debe dropearlos. Fichero /proc/sys/netipv4/icmp-echo-ignore-broadcast 1. Fichero icmp-echo-ignore-all 1. Fichero rep-filter 1 (o 2) verifica si el paquete es accesible desde esa interface de red.

### Herramientas
+ hping3
+ scapy
+ packit

### SYN flood
Intenta llenar la cola TCB abriendo muchísimas conexiones. Si esta se llena la máquina ya no aceptará más conexiones. Se puede modificar en /proc/sys/net/ipv4/tcp_max_back_log por defecto 128.

##### TCP SYN cookies
Fichero  /proc/sys/net/ipv4/tcp_syncookies. Guardan la información mínima para abrir conexiones.

##### SYN proxies
Evita que las máquinas en lugar de abrir conexiones contra la máquina las abra el syn proxy y hace el handshake. Cuando está hecha le pasa la conexión a la máquina. Otra solución son las SYN cachés. 

### Ataques por UDP
Son mucho más dañinos porque simplemente se envían cosas, no se puede cortar tan fácil el handshake. Se pueden hacer con udpflood.

### Ataque al STP
Si configuras la máquina como rootbridge te cragas tda la organización.

### Tráfico
Dudoso, legítimo o dudosos. Se gestiona con qos. Deja pasar con prioridad el tráfico legítimo, dropea el tráfico dudoso y deja pasar con menos prioridad el tráfico dudoso.

