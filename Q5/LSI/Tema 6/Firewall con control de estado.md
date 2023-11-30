[[Tema 6-Monitorización y filtrado]]

### Control de estados
+ New: cuando se envía el SYN
+ Established: una vez hecho el SYN
+ Related: conexiones relacionadas, por ejemplo, un error ICMP, cuando los FTP abren una conexión en un puerto bajo una vez y luego en un puerto alto...

### Métodos
##### Primer método
+ iptables -A input -p tcp -dport 22 -s 10.11.30.0/24 -d 10.11.48.miIP -m contrack --cstate new, established -j accept 
+  iptables -A output -p tcp -sport 22 -s  10.11.48.miIP -d 10.11.30.0/24 -m contrack --cstate established, related -j accept
+ iptables -A input -p tcp -j reject --reject-with tcp-reset
+ iptables -A input -p udp -j reject --reject-with icmp-port-unrechable

Se puede hacer multipuerto: -m multiport --dport 22,80,443...

##### Segundo método
+ iptables -A input -m contrack --cstate established, related -j accept
+ iptables -A output -m contrack --cstate established, related -j accept
+ iptables -A input -p tcp -dport 22 -s 10.11.30.0/24 -d 10.11.48.miIP -m contrack --cstate new -j accept 

### UDP
El primer paquete udp que llega a ip tables lo marca como no atentido, simulando ser un SYN. Por tanto se puede controlar el UDP en los firewall de control de estado. 

### Firewall persistente
+ iptables -nL --line-number  # Lista el conjunto de reglas

Un firewall persistente se puede hacer con un servicio, se puede hacer con un post-up (/ruta/del/script) en el fichero de interfaces, se puede hacer con iptables-persistent...

+ ystemctl 0 iptables-persistent
+ iptables -save > /etc/iptables.v4
+ iptables -restore < /etc7iptables.v4

También se puede con ip6tables.

+ iptables -A input -p tcp --dport 80 -m string --string "/etc/passwd" -j log --log-ip-optink --log-tcp-optim --log-prefix "password" 
+  iptables -A input -p tcp --dport 80 -m string --string "/etc/passwd" -j drop
+  iptables -A input -p tcp --dport 22 -j log "intento fallido ssh" --log-level 4

Ahora en rsyslog.conf:
:msg, contains, "intento fallido ssh" /var/log/ssh...
~stop

### Netfilter
Framework que permite interactuar con los paquetes de red en todas sus fases. Dos de las utilidades que tiene son: iptables y nftables. 
+ iptables -t filter -A forward -s x.x.x.x -d x.x.x.x -p tcp --dport 514 -m contrack --cstate new -j accept
+ nft add rule filter forward ip saddr x.x.x.x ip daddr x.x.x.x tcp dport 514 ct state new accept

Se diferencia de iptables en que nft contiene todo 8en iptabñes tenemos iptables, ip6tables...)

### Psad
Es una herramienta que analiza todos los logs del firewall para prevenir ataques a la máquina. Es una adaptación de snort. También se puede hacer de forma gráfica con GUI neft o Fwbuilder. O usando herramientas como ufw.

### FC(algo)
Es un protocolo de comunicación entre firewall que comprueba si están funcionando correctamente.