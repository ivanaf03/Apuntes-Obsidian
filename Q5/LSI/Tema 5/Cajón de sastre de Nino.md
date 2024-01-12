[[Tema 5-DoS y monitorización]]

## Regla de firewalls
+ iptables -A INPUT -p tcp --dport 80 -m hashlimit --hashlimit-mode srcip --hashlimit-name http --hashlimit-htable-expire 300000 --hashlimit-above 15/minute -j ACCEPT

+ iptables -A INPUT -p tcp --dport 22 -m hashlimit --hashlimit-mode srcip --hashlimit-name ssh --hashlimit-htable-expire 300000 --hashlimit-above 15/minute --hashlimit-burst 1 --hashlimit-srcmask 32 --hashlimit-htable-max 4000000 -j ACCEPT

Ambas reglas están diseñadas para limitar la tasa de tráfico entrante en función de la dirección IP de origen y el puerto de destino, proporcionando una medida de seguridad contra ciertos tipos de ataques, como ataques de fuerza bruta. Además, permiten un cierto número de paquetes por minuto antes de aplicar el límite, contribuyendo así a la gestión del tráfico.

## SMTP
Los sistemas de ficheros se pueden montar de muchísimas formas. Pasa lo mismo con los sistemas en el correo electrónico. Por ejemplo:
+ **Maildir:** miles de ficheros pequeños.
+ **Mailbox:** cada uno tiene su correo en un fichero.

## Pruebas de carga o estrés
Algunas herramientas para hacer pruebas de carga contra servidores  web. Por ejemplo:
+ jMeter
+ Apache Bench (ab)

## Private LAN y port isolation
Se hace con las DMZ. Se configura en ellas el port isolation, es decir, que máquinas no tengan conectividad con otras máquinas. Evita, por ejemplo, el pivoting. 

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

## Wifihammer
Es una herramienta que sirve para desautenticar a todos los wifis al alcance. También se puede montar un inhibidor de señal, por ejemplo, con un teléfono fijo inalámbrico. 