[[Tema 2-Information gathering]]

## ¿Qué es el fingerprinting?
Es la técnica de identificar características específicas de un dispositivo o servidor remoto. Estas características pueden incluir el sistema operativo, la versión del software, la configuración de red y otros detalles. Se realiza recopilando información sobre cómo el sistema responde a ciertas solicitudes de red y comparando esas respuestas con una base de datos de huellas dactilares conocidas. Ayuda a determinar el perfil de un sistema objetivo, lo que puede ser útil para identificar vulnerabilidades específicas o configuraciones inseguras.

Se usa para:
+ Detectar vulnerabilidades.
+ Crear exploits.
+ Inventariar la red.
+ Detectar dispositivos no autorizados.
+ Ingeniería social.

### Tipos
+ **Pasivo:** no interroga directamente a la máquina. Escucha la red y analiza la información. Puede utilizar solicitudes legítimas para obtener tráfico. Por ejemplo, la solicitud de una página web.
+ **Activo:** interroga a la máquina. Se basa en enviar paquetes a la máquina remota y analizar sus respuestas.

## Fingerprinting de SO
Se basa en identificar el sistema operativo de una máquina en una red. La idea principal es que cada sistema operativo tiene su propia implementación y configuración de la pila de protocolos, lo que puede resultar en comportamientos distintivos.

Un ejemplo muy simple es hacer un ping. Ahí se pueden ver los TTL se los paquetes. Por defecto en Windows es de 128 y en Linux de 64. Para cambiarlo en Linux:
```
# nano /etc/sysctl.conf
net.ipv4.ip_default_ttl = 64
```

Algunos campos de TCP/IP varían de un sistema operativo a otro. Gracias a esto podemos identificar mejor los SO. Por ejemplo:

| **Operating System**               | **IP Initial TTL** | **TCP Window Size** |
| ------------------------------ | -------------- | --------------- |
| Linux (kernel 2.4 and 2.6)      | 64             | 5840            |
| Google's customized Linux      | 64             | 5720            |
| FreeBSD                        | 64             | 65535           |
| Windows XP                     | 128            | 65535           |
| Windows 7, Vista and Server 2008| 128            | 8192            |
| Cisco Router (IOS 12.4)         | 255            | 4128            |
### nmap -O
Un ejemplo de salida podría ser:
```
# nmap -O -v scanme.nmap.org

Starting Nmap ( http://nmap.org )
Nmap scan report for scanme.nmap.org (74.207.244.221)
Not shown: 994 closed ports
PORT      STATE    SERVICE
22/tcp    open     ssh
80/tcp    open     http
646/tcp   filtered ldp
1720/tcp  filtered H.323/Q.931
9929/tcp  open     nping-echo
31337/tcp open     Elite

Device type: general purpose
Running: Linux 2.6.X
OS CPE: cpe:/o:linux:kernel:2.6.39
OS details: Linux 2.6.39
Uptime guess: 1.674 days (since Fri Sep 9 12:03:04 2011)
Network Distance: 10 hops
TCP Sequence Prediction: Difficulty=205 (Good luck!)
IP ID Sequence Generation: All zeros

Read data files from: /usr/local/bin/../share/nmap

Nmap done: 1 IP address (1 host up) scanned in 5.58 seconds
Raw packets sent: 1063 (47.432KB) | Rcvd: 1031 (41.664KB)
```

Los campos son:
+ **Device type:** tipo de dispositivos (router, printer, firewall, general purpose).
+ **Running:** familia y generación de SO.
+ **OS details/Aggressive OS guesses:** datos del SO en formato libre.
+ **Uptime guess:** estimación del tiempo que el sistema objetivo ha estado en funcionamiento.
+ **Network distance:** número de routers entre las máquinas.
+ **TCP Sequence Prediction:** estimación de la dificultad de realizar un ataque.
+ **IP ID Sequence Generation:** información sensible sobre sus niveles de tráfico, en función de cómo generan este campo.

## Fingerprinting de aplicaciones
Técnica que se utiliza para identificar el tipo y la versión específica de una aplicación que se está ejecutando en un puerto determinado. Aunque un puerto puede estar abierto, no garantiza necesariamente que se esté ejecutando el servicio esperado en ese puerto. En algunos casos, los administradores del sistema pueden cambiar la asignación de puertos para dificultar la identificación del servicio.

Se puede hacer con nmap -sV. Por ejemplo:
```
# nmap -sV -T4 localhost

Starting Nmap ( http://nmap.org )
Nmap scan report for felix (127.0.0.1)
(The 1640 ports scanned but not shown below are in state: closed)
PORT     STATE  SERVICE         VERSION
21/tcp   open   ftp             WU-FTPD wu-2.6.1-20
22/tcp   open   ssh             OpenSSH 3.1p1 (protocol 1.99)
53/tcp   open   domain          ISC BIND 9.2.1
79/tcp   open   finger          Linux fingerd
111/tcp  open   rpcbind         2 (rpc #100000)
443/tcp  open   ssl/http        Apache httpd 2.0.39 ((Unix) mod_perl/1.99_04-dev)
515/tcp  open   printer
631/tcp  open   ipp             CUPS 1.1
953/tcp  open   rndc?
5000/tcp open   ssl/ftp         WU-FTPD wu-2.6.1-20
5001/tcp open   ssl/ssh         OpenSSH 3.1p1 (protocol 1.99)
5002/tcp open   ssl/domain      ISC BIND 9.2.1
5003/tcp open   ssl/finger      Linux fingerd
6000/tcp open   X11             (access denied)
8000/tcp open   http-proxy       Junkbuster webproxy
8080/tcp open   http            Apache httpd 2.0.39 ((Unix) mod_perl/1.99_04-dev)
8081/tcp open   http            Apache httpd 2.0.39 ((Unix) mod_perl/1.99_04-dev)
Nmap done: 1 IP address (1 host up) scanned in 42.494 seconds
```

Si se escanea un puerto TCP específico, Nmap intenta establecer una conexión con ese puerto para interactuar con el servicio que pueda estar escuchando en ese puerto. Escucha durante 5 segundos, lo que se conoce como Null probe. Después:
+ Para protocolos como FTP, SSH, SMTP, Telnet, POP3, IMAP, entre otros, el servicio a menudo se identifica a sí mismo enviando una cabecera de bienvenida. Nmap analiza estas respuestas para obtener información sobre el servicio y su versión.
+ Si recibe datos Nmap compara las respuestas recibidas con las firmas y patrones almacenados en el archivo nmap-service-probes.

Si Nmap puede identificar completamente el servicio y su versión, se informa como "OK". Si la identificación es parcial ("soft match").

Es bueno combinar -s y -sV (usando -A por ejemplo). Si hay un proxy firewall que redirecciona las aplicaciones, con -O detectaremos el servidor donde se está ejecutando la aplicación.

## Otras técnicas de fingerprinting
+ **Direct Banner Grabbing:** práctica de obtener información sobre un servicio de red específico directamente del "banner" o encabezado que devuelve el servicio cuando se establece una conexión. Un banner es un mensaje informativo que el servicio envía al cliente cuando se establece una conexión. Este mensaje a menudo incluye detalles sobre la aplicación, la versión y otra información relevante. Por ejemplo:
```
# telnet nostromo.joeh.org 80

Trying 193.170.32.26...
[...]
HEAD / HTTP/1.0
[...]
Server: Microsoft-IIS/8.1
[...]
The analysis would reveal: ˆServer: Microsoft-IIS/8.1: It is a
Microsoft IIS, version 8.1.
```
+ **Indirect Banner Grabbing:** práctica de obtener información sobre un servicio de red específico sin conectarse directamente al servicio, utilizando métodos indirectos o técnicas que no implican establecer una conexión real. A diferencia del Direct Banner Grabbing, que implica una conexión activa al servicio, el Indirect Banner Grabbing utiliza métodos que no interactúan directamente con el servicio, lo que puede ser beneficioso en términos de sigilo y evasión de detección.
+ **Fingerprinting a nivel ASCII:** con netcat es posible conectarse a cualquier máquina con puertos abiertos. Normalmente en una conexión lo primero es el paso de heaps o cabeceras. Por defecto el servidor suele decir de qué tipo es y qué módulos tiene abiertos. Securizar esto es tan fácil como modificar las cabeceras.
+ **Fingerprinting a nivel TCP-IP:** identificar sistemas operativos, servicios o aplicaciones en una red determinada mediante la observación y análisis de sus respuestas a solicitudes TCP/IP. La forma se securizarla es similar al nivel ASCII, cambiando las cabeceras.
+ **Fingerprinting a nivel ICMP:** identificar sistemas o dispositivos en una red al analizar y evaluar sus respuestas a los mensajes ICMP. Al igual que el anterior se basa en enviar paquetería a todos los operativos. Para securizarlo podemos filtrar el tráfico ICMP.

### Securización de Apache
Una forma de securizar un servidor apache es en el fichero /etc/apache/apache2.conf es modificar los servertokens, un parámetro controla qué información sobre la versión del servidor se incluye en la respuesta HTTP; y la serversignature, un parámetro controla si se incluye la información del servidor en el encabezado de las páginas de error generadas por Apache. Cuanto menos información demos mejor. Así cuando le pidan las HEAD no dará apenas información. Para verlo usamos:

```
lynx -head -dump http://www.udc.es
```

Otra herramienta para sacar que información está corriendo en la máquina atacada es Whatweb. 

## Herramientas
+ Xprobe2 (activo) 
+ p0f (pasivo) 
+ NetworkMiner (pasivo) 
+ Ettercap. TCP/IP stack fingerprinting (pasivo) 
+ ZMap (activo)

Para análisis de redes en Windows podemos usar NetScan.

## Medidas de ofuscación o scrubbing
### 1ª gen-ASCII
Esta capa puede implicar la representación de datos en formato ASCII para dificultar la interpretación directa.

### 2ª gen-TCP/IP
Esta capa puede manipular parámetros específicos del protocolo TCP/IP, como el Time-to-Live (TTL). Por ejemplo:
```
echo 128 > /proc/sys/net/ipv4/ip_default_ttl
```

### 3ª gen-ICMP
La capa ICMP se utiliza para mensajes de control y errores en la red. Una técnica común es la "fragmentación de paquetes ICMP" en la capa de red.

### 4ª gen-capa aplicación
En esta capa se realiza manipulación de datos a nivel de aplicación. Puede incluir técnicas específicas para ofuscar la identidad del sistema operativo, como las proporcionadas por herramientas como OSfuscate. 

El comando iptables permite configurar un firewall. La evolución de este comando se llama ntf. Por ejemplo, este comando modifica el TTL de todo paquete que pase por el firewall:
```
iptables -t MANGLE -I OUTPUT -j TTL -ttl-set 53
```

