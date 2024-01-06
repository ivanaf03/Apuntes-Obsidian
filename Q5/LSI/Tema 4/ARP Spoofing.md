[[Tema 4-Sniffing]]

### Tipos
##### MIMT

##### ICMP redirects
Si envío este tipo de paquetes a una máquina me puede poner como router default. Es un half MIMT, normalmente los routers no aceptan ICMP redicrect. Se hace con:
```
ettercap -M icmp -f mac/gateway /x.x.x.x//
```

Ficheros send_redirects, source_redirects y all_accepts_redirects. Se puede configurar directamente en /etc/sysctl.conf y reiniciar con "sysctl -p". Accept_source_routing es la flag del path addresing, que sirve para indicra por donde quiero que salgan mis paquetes. 

##### DHCP spoofing
Se hace con:
```
ettercap -Tq -M dhcp: x.x.x.x/submask/router/DNS /x.x.x.x//
```

Lo que se hace es configurar que puertos permiten dhcp offers para evitar el DHCP spoofing. Esto se llama DHCP snooping.

##### Port stealing
Los conmutadores tienen de forma dinámica asignada una mac a cada puerto. El robo de puerto consiste en hacer un flood al puerto destino para que el conmutador asigne nuestra MAC como destino. Se hace con:
```
ettercap -M port ([remote][tree]) /x.x.x.x// #sin tree la MAC será la de uestra propia máquina
```

##### NDP
Se hace con:
```
ettercap -M ndp //fe80:.../
```

##### DNS spoofing
En /etc/ettercap/etter.dns se pueden añadir cosas como www.google.es A 10.11.48.25. Luego se hace:
```
ettercap -Tq -i ens33 -P dns_spoof -f repoison_arp -P sslstricp -M /10.11.48.x// ///
```

Para securizar el DNS se hace con DNSSec. Es un protocolo seguro que garantiza autenticación, integridad de datos mediante registros dns key... Pero no cifra, nos pueden interceptar las peticiones dns. Eso sí, evita el dns spoofing. Para cifrarlo se puede hacer con DOT (DNS over TLS). 

Evilgrade es una herramienta que permite, si estamos haciendo MIMT, inyecta en las actualizaciones de windows o linux troyanos.

### Opciones de arp
+ arp -a
+ arp -d
+ arp -s

arptables -A input -s source -j DROP
ip link set dev ens33 arp off (desactyiva el protocolo arp de la máquina)
ip neigh flush all (borra la tabla arp)

Las distros linux más modernas tienen dos ficheros, gcc_stable_time y base_rechable_time (antes solo era uno, gc_state_time) que permiten configurar un rango de refresco de tablas arp.

nast -c avisa si una ip ha cambiado de mac (arp spoofing o arp poisoning).

### MAC flooding
Se hace con un plugin de ettercap llamado manflood. Busca sobrecargas en los conmutadores de red. Baja el rendimiento de los paquetes hasta el punto de que empiecen a funcionar como un hub o se caen. Para protegernos del mac flooding se hace con unicast flooding protection, que limita el ancho de banda de las MAC que llegan a los puertos de un conmutador. También existe port security, que delimita el número de MAC que puede haber en un puerto.

### Port span o port mirroring
Consiste en clonar el tráfico de algunos puertos a un puerto a mayores. Puede dar problemas de cuello de botella. Para evitar esto existe el trunk de puertos, que en vez de coger un puerto, coge 2, por ejemplo, y los configura como un solo interfaz de red con el doble de ancho de banda. También se conoce como link aggregation, lag, port channel...

### Boundings
Se hace con el comando ifenslave. Se hace en el fichero /etc/modules con echo>>bounding. Estos modos son:
+ Mode 0 RR
+ Mode 1 Active-backup
+ Mode 2 XOR
+ Mode 3 Broadcast
+ Mode 4 802.3 AD
+ Mode 5 Balance-TLB
+ Mode 6 Balance-ALB

En el fichero interfaces:
```
iface bound inet static
adress x.x.x.x
...
slaves ens33 ens34 ens35
bound_mode 0  # Para Round Robin
```

### DHCP snooping
Se utiliza para mitigar ataques de suplantación de DHCP (Dynamic Host Configuration Protocol). El protocolo DHCP se utiliza para asignar direcciones IP de manera dinámica a dispositivos en una red, como computadoras y dispositivos móviles. Sin embargo, si un atacante se hace pasar por un servidor DHCP falso, podría asignar direcciones IP maliciosas a dispositivos y comprometer la seguridad de la red.

### Port security
Por defecto permite solo una mac asociada a cada puerto y el modo shutdown, si se produce una vulneración en ese puerto tira la paquetería y deshabilita el puerto.
```
switchl port-security maximum 4
```

```
switchl port-security mac-address xx:xx..:xx
```

```
switchl port-security violation protect (o violation restrict)
```

### TAP
Los Test Access Ports son dispositivos que se suelen montar entre los router y firewall. Permite la monitorización del tráfico de red en tiempo real sin afectar el flujo normal de datos. Los TAPs pueden utilizarse para la depuración de redes, el análisis del tráfico, la monitorización de la seguridad y otras tareas de diagnóstico.

### Firewall de nueva generación
Tienen WAT, hipervisores para virtualizar todas las máquinas. Trabajan a todos los niveles e incluyen sistemas de prevención de intrusiones. Están vinculados a los sistemas de autenticación. Pueden analizar el tráfico en busca de malware. Suelen cortar el cifrado. 

Empresas de firewalls de palo alto:
+ Cisco
+ Jupiter
+ Checkpoint

### SIEM (Sistemas de Gestión de Eventos)
Por ejemplo, splunk, prelude, arcsight, logrytm... Por ejemplo, el del CESGA está montado con Apache Hadoop. Se suelen usar sistemas de ficheros distribuidos, como HSFS, y modelos de programación, como map reduce. Los SOC están vinculados al SIEM, que trabajan con logs. A mayores también están vinculados a EDR, que trabajan con agentes. Sirven para securizar hosts finales.

### SORBS (Spam and Open Relay Blocking System)
Es un servicio y una base de datos que se utiliza para identificar y bloquear servidores de correo electrónico que pueden ser utilizados para enviar correo basura (spam) o que presentan vulnerabilidades de retransmisión abierta. Fue creado para ayudar a las organizaciones y proveedores de servicios de Internet (ISPs) a reducir la cantidad de correo no deseado que llega a sus usuarios y prevenir el abuso de servidores de correo.

### Robar tráfico en https
Una forma es con inyección en el certificado. Se puede hacer con sslstrip o sslstrip2, que intentan saltarse HSTS. Las máquinas no deben estar haciendo routing, ip forwarding, DHCP, etc.