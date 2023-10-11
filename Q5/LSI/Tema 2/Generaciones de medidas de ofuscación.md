[[Tema 2-Information gathering]]

##### 1 gen-ASCII

##### 2 gen-TCP/IP

##### 3 gen-ICMP

##### 4 gen-capa aplicación
Se utilizan medidas de ofuscación, por ejemplo para el TTL. Las máquinas windows suelen usar un TTL de 128 y las UNIX de 64. En windows está en el registro del sistema. En linux se puede cambiar con:
```
echo 128>/proc/sys/net/ipv4/ip_default_ttl
```

El comando iptables permite configurar un firewall. La evolución de este comando se llama ntf. Por ejemplo, este comando modifica el TTL de todo paquete que pase por el firewall:
```
iptables -t MANGLE -I OUTPUT -j TTL -ttl-set 53
```

Existen otras como OSfuscate. Si alguien te fingerprintea, te ajusta el operativo para hacerte pasar por otro.

### Servidores
Una forma de securizar un servidor apache es en el fichero /etc/apache/apache2.conf es modificar los servertokens y la serversignature. Cuanto menos información demos mejor. Así cuando le pidan las HEAD no dará apenas información. Para verlo usamos:
```
lynx -head -dump http://www.udc.es
```

Otra herramienta para sacar que información esta corriendo en la máquina atacada es whatweb.

### SMTP y nmap
Tiene dos directivas:
+ **Verify:** Al conectarte se ve si el usuario existe. Se suele desactivar.
+ **RCPT TO:** Especifica la dirección de correo del destinatario.

Para atacar esto podemos usar:
```
smtp-user-enum -m vrfy/rcpt -U user.txt -T server.txt 
```

El SYN scan también se llama STEALTH. Se puede hacer con:
```
hping3 -c 1 -S -p 80 x.x.x.x

nmap -sS/-sF/-sA -p 80 x.x.x.x --packet-trace
```

```
nmap x.x.x.x # host-discovery+port-scanning a todas las máquinas
```

##### Estados de nmap
+ Open: Abierto, algo corriendo
+ Closed: Cerrado, no hay nada escuchando ahí. Pero el puerto está siendo atendido
+ Filtered: Hay algo en medio, por ejemplo un firewall
+ Unfiltered: Puerto accesible, pero no se sabe si está abierto o cerrado
	+ Openfiltered
	+ Closedfiltered

##### Opciones
+ -6: ipv6
+ -O: fingerprinting de SO
+ -sV: fingerprinting de servicios o puertos
+ -sP: host discovery

### Netscan
Sirve para comprobar los estados de red en Microsoft