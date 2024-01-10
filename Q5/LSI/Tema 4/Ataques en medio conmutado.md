[[Tema 4-Sniffing]]

## ARP Spoofing
Es una técnica para infiltrarse en red Ethernet conmutada. Permite al atacante leer paquetes de datos en la LAN, modificar el tráfico o detenerlo. El atacante intenta asociar su MAC con la IP de la víctima.

El protocolo ARP envía un paquete (ARP request) ,a la dirección de difusión de la red, que contiene la dirección IP por la que se pregunta, y se espera a que esa máquina (u otra) responda (ARP reply) con la dirección Ethernet que le corresponde.

Se puede hacer con ettercap, Cain y Abel, Dsniff... Se puede prevenir con MACs estáticas en caché ARP. Se puede detectar con wireshark, nast, arpwatch, ettercap, sentinel, ArpOn...

### ARP
Cada máquina mantiene una caché con las direcciones traducidas para reducir el retardo y la carga: caché ARP. Las entradas de la tabla se borran cada cierto tiempo, ya que las direcciones físicas de la red pueden cambiar. Si una IP se encuentra en la tabla, la máquina ya no enviará ARP request. Cuando un máquina recibe un ARP reply, sea o no solicitado, actualiza la caché ARP. Si una IP ya está en la caché ARP y se recibe un ARP reply de la misma IP, pero con una MAC diferente, se actualiza la caché ARP.

![[arp spoofing.png]]
Con el comando arp podemos:
+ **arp -a:** muestra la tabla ARP.
+ **arp -d:** borra una entrada en la tabla.
+ **arp -s:** agrega una entrada a la tabla.

arptables -A input -s source -j DROP
ip link set dev ens33 arp off (desactyiva el protocolo arp de la máquina)
ip neigh flush all (borra la tabla arp)

Las distros linux más modernas tienen dos ficheros, gcc_stable_time y base_rechable_time (antes solo era uno, gc_state_time) que permiten configurar un rango de refresco de tablas arp.

nast -c avisa si una ip ha cambiado de mac (arp spoofing o arp poisoning).

### ICMP redirects
Si envío este tipo de paquetes a una máquina me puede poner como router default. Es un half MIMT, normalmente los routers no aceptan ICMP redicrect. Se hace con:
```
ettercap -M icmp -f mac/gateway /x.x.x.x//
```

Ficheros send_redirects, source_redirects y all_accepts_redirects. Se puede configurar directamente en /etc/sysctl.conf y reiniciar con "sysctl -p". Accept_source_routing es la flag del path addresing, que sirve para indicra por donde quiero que salgan mis paquetes. 

### DHCP spoofing
Se hace con:
```
ettercap -Tq -M dhcp: x.x.x.x/submask/router/DNS /x.x.x.x//
```

Lo que se hace es configurar que puertos permiten dhcp offers para evitar el DHCP spoofing. Esto se llama DHCP snooping.

### Port stealing
Los conmutadores tienen de forma dinámica asignada una mac a cada puerto. El robo de puerto consiste en hacer un flood al puerto destino para que el conmutador asigne nuestra MAC como destino. Se hace con:
```
ettercap -M port ([remote][tree]) /x.x.x.x// #sin tree la MAC será la de nuestra propia máquina
```

### NDP
Se hace con:
```
ettercap -M ndp //fe80:.../
```

### DNS spoofing
En /etc/ettercap/etter.dns se pueden añadir cosas como www.google.es A 10.11.48.25. Luego se hace:
```
ettercap -Tq -i ens33 -P dns_spoof -f repoison_arp -P sslstricp -M /10.11.48.x// ///
```

Para securizar el DNS se hace con DNSSec. Es un protocolo seguro que garantiza autenticación, integridad de datos mediante registros dns key... Pero no cifra, nos pueden interceptar las peticiones dns. Eso sí, evita el dns spoofing. Para cifrarlo se puede hacer con DOT (DNS over TLS). 

Evilgrade es una herramienta que permite, si estamos haciendo MIMT, inyecta en las actualizaciones de windows o linux troyanos.

## CAM flooding
Se hace con un plugin de ettercap llamado rand_flood.

Busca sobrecargas en los conmutadores de red. Los switches mantienen una tabla que mapea direcciones MAC a puertos físicos de switch (tabla CAM). Esto permite al switch dirigir datos sólo al puerto físico en el que se encuentra el destinatario.

Baja el rendimiento de los paquetes hasta el punto de que empiecen a funcionar como un hub o se caen. Para protegernos del mac flooding se hace con unicast flooding protection, que limita el ancho de banda de las MAC que llegan a los puertos de un conmutador. También existe port security, que delimita el número de MAC que puede haber en un puerto.

## Port stealing
El atacante envía multitud de tramas ARP (pero no con el objetivo de saturar la CAM). El objetivo es que el switch "aprenda" que la víctima se encuentra en ese puerto y así dirija el tráfico hacia él. Es decir, se le "roba" el puerto a la víctima. 

Una vez que el atacante recibe paquetes "robados", detiene el proceso de inundación y realiza un ARP request a la víctima (destino real del paquete). Esto provocará que la víctima recupere su puerto. En cuanto el atacante recibe el ARP reply sabe que la víctima ha recuperado su puerto, y le reenvía los paquetes robados. Entonces se puede reiniciar el proceso de inundación esperando nuevos paquetes. Se puede hacer con:
```
ettercap -T -M port:remote /10.0.0.1// /10.0.0.15//
```
