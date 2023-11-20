[[Tema 5-DoS]]

## Regla de firewalls
+ iptables -A input -p tcp --dport 80 -m hashlimit ... http -j ACCEPT
+ iptables -A input -p tcp --dport 22 -m hashlimit --hash-limit-mode srcip ... --contract --cstate NEW -j ACCEPT

## Trafic shaping y packet shaping
Están vinculados a QoS. Permiten aguantar mejor los ataques DDoS. También se suelen usar reverse proxys para ello. Funcionan de forma que para que las máquinas que entran a los servidores web de una organización desde internet tengan que pasar por ellos.

## SMTP
Los sistemas de ficheros se pueden montar de muchísimas formas. Pasa lo mismo con los sistemas en el correo electrónico. Por ejemplo:
+ Maildir: miles de ficheros pequeños
+ Mailbox: cada uno tiene su correo en un fichero

## Pruebas de carga o estrés
Algunas herramientas para hacer pruebas de carga contra servidores  web. Por ejemplo:
+ jMeter
+ Apache Bench (ab)

## Private LAN y port isolation
Se hace con las DMZ. Se configura en ellas el port isolation, es decir, que máquinas no tengan conectividad con otras máquinas. Evita, por ejemplo, el pivoting. 

## Inyectores de paquetes
Por ejemplo, un floodeo SYN:
+ packit -b 0 -c 0 -sR -d 10.11.49.49 -F s -S 1000 -O 80 # Se puede jugar con la flag -S para que el firewall deje pasar las salidas a ese puerto
+ hping3 -S -p 80 --flood --rand-source 10.11.49.49
+ hping3 -S 10.11.48.100 -a 10.11.48.100 ...  # LAN atack, la ip origen y destino es la misma. Se autoinunda, pero ya no funciona en los kernel actuales.

## IPV6
En ipv6 tenemos NDP y SNDP (con PKI). El protocolo SLAAK es lo que utiliza ipv6 para dar ipv6. 
+ fake_roter6 # envía paquetes RA a todas las máquinas para que estén continuamente reconfigurando las ipv6 de link-local.

Podemos regular las cuotas en /proc/sys/net/ipv6 o en systemctl.conf

## HTML
```
<meta httrequiv="refresh" contente="3">
<iframe src="http://in- with="0"></iframe>
```

Hoy en día los servidores suelen cortar los iframes. Algunas técnicas son framekiller, framebuster...

## Slowloris
Abren muchas conexiones con cabeceras sin rotorno de línea. Esto ralentiza la conexión.

Otro modo es el slow POST. Hace peticiones muy lentas y envía poco a poco las cosas para ralentizar las conexiones.

Otro modo es el slow READ. Hace algo de forma similar con peticiones GET.

Herramienta de denegación de servicio https (thc hacker choice). Otra es Tor shammer, que hace ataques POST pero a través de la red Tor. Ven las IP del exit node Tor.