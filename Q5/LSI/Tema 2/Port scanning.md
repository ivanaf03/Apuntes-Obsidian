[[Tema 2-Information gathering]]

### ¿Qué es el port scanning?
Consiste en testear de forma remota varios puertos para determinar su estado. Se hace por seguridad. Reducir el número y complejidad de los servicios ofrecidos reduce la oportunidad de que los atacantes entren. La herramienta por excelencia que se usa es nmap.
### Puertos
Un puerto es una abstracción usada para identificar y direccionar aplicaciones o servicios en un host dentro de una red. Van del 0 al 65535. En las conexiones TCP y UDP la conexión se identifica como IP+puerto origen / IP+puerto destino.

##### Estados de un puerto según nmap
+ **Open:** Abierto, una aplicación está aceptando conexiones TCP o paquetes UDP
+ **Closed:** Cerrado, no hay ninguna aplicación escuchando ahí. Pero el puerto está siendo atendido
+ **Filtered:** El filtrado de paquetes impide que las pruebas alcancen el puerto, por ejemplo un firewall o las reglas de un router
+ **Unfiltered:** Puerto accesible, pero nmap no sabe si está abierto o cerrado
+ **Open|filtered:** Nmap no es capaz de saber si está abierto o filtrado
+ **Closed|filtered:** Nmap no es capaz de saber si está cerrado o filtrado

##### Clasificación de puertos según IANA
+ **Well-known-ports:** Puertos entre el 1 y el 1023 registrados para un determinado servicio. Por ejemplo, el 22 para SSH o el 80 para HTTP. En algunos sistemas se exigen permisos especiales para asociar aplicaciones a estos puertos.
+ **Registered ports:** Puertos entre el 1024 y el 49151, registrados por IANA, que no exigen privilegios especiales.
+ **Puertos privados o dinámicos:** Puertos entre el 49152 y el 65535 que se usan 

### Escaneo de puertos con nmap
Nmap por defecto ya hace port scanning. Pero existen muchas flags que permiten otros métodos de escaneo de puertos:
+ **-sS**: es lo mismo que el escaneo default. Es discreto, ya que no completa las conexiones TCP, pero puede haber firewalls y IDS que detecten los escaneos SYN. Requiere de privilegios raw packet, es decir, capacidad para manipular paquetes de red a nivel de socket crudo (raw socket). Esto implica la capacidad de trabajar directamente con paquetes de datos de red sin restricciones de acceso o inspección por parte del sistema operativo o de los mecanismos de seguridad. Los raw sockets permiten a una aplicación o proceso enviar y recibir paquetes de red sin restricciones y sin la necesidad de utilizar los protocolos y servicios de red de más alto nivel proporcionados por el sistema operativo. Si un puerto responde un TCP SYN/ACK está abierto, si responde un TCP RST está cerrado y si no responde o envía un ICMP unreachable está filtrado.
+ **-sT:** escaneo por defecto cuando SYN scan no se puede realiza, ya sea por que son redes ipv6 o por falta de privilegios. Nmap solicita al sistema operativo subyacente que establezca una conexión completa con la máquina y el puerto objetivo. Para ello, utiliza la llamada al sistema "connect()".  En el escaneo SYN      ( "-sS"), se envía un paquete SYN al puerto objetivo, y si el puerto está abierto, el sistema responderá con un paquete SYN-ACK. Luego, se envía un paquete RST (reset) para cerrar la conexión sin completarla por completo. En cambio, en el escaneo de conexión completa ("-sT"), se establece una conexión completa enviando los paquetes SYN y ACK en ambos sentidos. Esto significa que se completa una "conexión" real con el puerto objetivo, en lugar de simplemente iniciar una y luego cancelarla (half-open reset). Solo sirve en puertos abiertos.
+ **-sU:** escaneo UDP que envía la cabecera UDP vacía a cada puerto. Si un puerto responde está abierto, si no responde está abierto o filtrado, si responde con un error ICMP unreachable tipo 3 código 3 está cerrado y si responde cualquier otro error ICMP unreachable tipo 3 está filtrado.

##### Idle scan
Es una técnica de escaneo de puertos utilizada en ciberseguridad y pruebas de penetración para determinar si un puerto específico en un sistema objetivo está abierto o cerrado, sin alertar directamente al sistema objetivo ni dejar rastros en los registros del sistema. Esta técnica se basa en la explotación de la propiedad de los sistemas TCP/IP de mantener la coherencia en la numeración de secuencia de los paquetes y en la utilización de sistemas intermedios (como un firewall o un host zombie) para llevar a cabo el escaneo.

Se hace con:
```
nmap -p0 -p 80 -sI x.x.x.x www.maquina.com
```

Lo que hace en enviar un syn-ack a la máquina zombie, a lo que responderá con un rst. Luego se enví un syn con la IP del zombie. Si el puerto está abierto el zombie recibe un syn-ack. A lo que responde con un rst. Luego se envía un syn ack al zombie, a lo que responde con otro rst. Si el puerto está abierto, el ip id se habrá aumentado en 2. Los kernels modernos ya no utilizan ip id secuenciales para evitar esto.

### IP spoofing
Cuando antes enviábamos el syn con una IP suplantada a la máquina que atacábamos, lo que estábamos haciendo era IP spoofing. Consiste en enviar paquetes con una IP falsa. Los routers se pueden configurar para rechazar los paquetes con una IP que no pertenezca a la red.
