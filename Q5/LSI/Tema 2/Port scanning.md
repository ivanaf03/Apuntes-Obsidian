[[Tema 2-Information gathering]]

## ¿Qué es el port scanning?
Consiste en testear de forma remota varios puertos para determinar su estado. Se hace por seguridad. Reducir el número y complejidad de los servicios ofrecidos reduce la oportunidad de que los atacantes entren. La herramienta por excelencia que se usa es nmap.

## Puertos
Un puerto es una abstracción usada para identificar y direccionar aplicaciones o servicios en un host dentro de una red. Van del 0 al 65535. En las conexiones TCP y UDP la conexión se identifica como IP+puerto origen / IP+puerto destino.

### Estados de un puerto según nmap
+ **Open:** Abierto, una aplicación está aceptando conexiones TCP o paquetes UDP
+ **Closed:** Cerrado, no hay ninguna aplicación escuchando ahí. Pero el puerto está siendo atendido.
+ **Filtered:** El filtrado de paquetes impide que las pruebas alcancen el puerto, por ejemplo un firewall o las reglas de un router.
+ **Unfiltered:** Puerto accesible, pero nmap no sabe si está abierto o cerrado.
+ **Open|filtered:** Nmap no es capaz de saber si está abierto o filtrado.
+ **Closed|filtered:** Nmap no es capaz de saber si está cerrado o filtrado.

Algunas veces una combinación de tipos de escaneo puede usarse para recoger información extra de un sistema. Si un tipo de escaneo identifica un puerto como open|filtered y otro lo identifica como unfiltered, por lógica e puerto está open. Aunque a veces no se cumple.

### Clasificación de puertos según IANA
+ **Well-known-ports:** Puertos entre el 1 y el 1023 registrados para un determinado servicio. Por ejemplo, el 22 para SSH o el 80 para HTTP. En algunos sistemas se exigen permisos especiales para asociar aplicaciones a estos puertos.
+ **Registered ports:** Puertos entre el 1024 y el 49151, registrados por IANA, que no exigen privilegios especiales.
+ **Puertos privados o dinámicos:** Puertos entre el 49152 y el 65535 que se usan 

### Escaneo de puertos con nmap
Nmap por defecto ya hace port scanning. Pero existen muchas flags que permiten otros métodos de escaneo de puertos:
+ **-sS**: es lo mismo que el escaneo default. Se llama SYN scan o STEALTH. Es discreto, ya que no completa las conexiones TCP, pero puede haber firewalls y IDS que detecten los escaneos SYN. Requiere de privilegios raw packet, es decir, capacidad para manipular paquetes de red a nivel de socket crudo (raw socket). Esto implica la capacidad de trabajar directamente con paquetes de datos de red sin restricciones de acceso o inspección por parte del sistema operativo o de los mecanismos de seguridad. Los raw sockets permiten a una aplicación o proceso enviar y recibir paquetes de red sin restricciones y sin la necesidad de utilizar los protocolos y servicios de red de más alto nivel proporcionados por el sistema operativo. Si un puerto responde un TCP SYN/ACK está abierto, si responde un TCP RST está cerrado y si no responde o envía un ICMP unreachable está filtrado. También se puede usar hping3:
```
hping3 -c 1 -S -p 80 x.x.x.x
```
+ **-sT:** escaneo por defecto cuando SYN scan no se puede realiza, ya sea por que son redes ipv6 o por falta de privilegios. Nmap solicita al sistema operativo subyacente que establezca una conexión completa con la máquina y el puerto objetivo. Para ello, utiliza la llamada al sistema "connect()".  En el escaneo SYN ( "-sS"), se envía un paquete SYN al puerto objetivo, y si el puerto está abierto, el sistema responderá con un paquete SYN-ACK. Luego, se envía un paquete RST (reset) para cerrar la conexión sin completarla por completo. En cambio, en el escaneo de conexión completa ("-sT"), se establece una conexión completa enviando los paquetes SYN y ACK en ambos sentidos. Esto significa que se completa una "conexión" real con el puerto objetivo, en lugar de simplemente iniciar una y luego cancelarla (half-open reset). Solo sirve en puertos abiertos.
+ **-sU:** escaneo UDP que envía la cabecera UDP vacía a cada puerto. Si un puerto responde está abierto, si no responde está abierto o filtrado, si responde con un error ICMP unreachable tipo 3 código 3 está cerrado y si responde cualquier otro error ICMP unreachable tipo 3 está filtrado. 
+ **-sV:** se utiliza para realizar un escaneo de versiones. Envía solicitudes específicas a los puertos abiertos y analiza las respuestas para determinar la versión del servicio. "nmap-service-probes" es un archivo de texto que contiene patrones de fingerprints de servicios específicos, lo que permite a Nmap reconocer y clasificar servicios en función de las respuestas a ciertos paquetes de red. 
+ **-sA:** escaneo que no determina si el puerto está open o open|filtered. Se usa para averiguar las reglas de los firewalls, determinando si son stateful o no y qué puertos se filtran. Envía paquetes con solo el flag de ACK. Si no están filtrados devuelven un RST. Si no responden o responden un error ICMP están filtrados.
+ **-sF, -sN, -sX:** escaneos que atraviesan firewall sin control de estado o routers que hacen filtrado de paquetes. Averiguan si un puerto está cerrado respondiendo un RST. -sF fija el flag FIN, -sN no dija ningún flag y -sX sija FIN, PSH y URG.

### Idle scan
Es una técnica de escaneo de puertos utilizada en ciberseguridad y pruebas de penetración para determinar si un puerto específico en un sistema objetivo está abierto o cerrado, sin alertar directamente al sistema objetivo ni dejar rastros en los registros del sistema. Esta técnica se basa en la explotación de la propiedad de los sistemas TCP/IP de mantener la coherencia en la numeración de secuencia de los paquetes y en la utilización de sistemas intermedios (como un firewall o un host zombie) para llevar a cabo el escaneo.

Se hace con -sI y una máquina zombie. Un ejemplo sería:
```
nmap -p0 -p 80 -sI x.x.x.x www.maquina.com
```

Lo que hace en enviar un SYN-ACK a la máquina zombie, a lo que responderá con un RST. Luego se envía un SYN con la IP del zombie. Si el puerto está abierto el zombie recibe un SYN-ACK. A lo que responde con un RST. Luego se envía un SYN ACK al zombie, a lo que responde con otro RST. Si el puerto está abierto, el IP ID se habrá aumentado en 2. Los kernels modernos ya no utilizan IP ID secuenciales para evitar esto. Si está cerrado o filtrado solo habría aumentado en 1.

### Tiempo de escaneo
La opción -T de nmap permite ajustar el nivel de agresividad con la que se hace un escaneo. Estos son los modos que utiliza:
- **paranoid (0):** Este modo es el más lento y está diseñado para evadir sistemas de detección de intrusiones (IDS). Es útil cuando se busca realizar un escaneo muy sigiloso y minimizar la detección.
- **sneaky (1):** Similar al modo `paranoid`, este nivel también busca evadir IDS, pero es un poco más rápido.
- **polite (2):** Consumo de ancho de banda mínimo, útil cuando se desea minimizar el impacto en la red.
- **normal (3):** Configuración por defecto, un equilibrio entre velocidad y precisión.
- **aggressive (4):** Acelera el escaneo, asumiendo una red rápida y fiable. Aumenta la velocidad, pero puede ser más detectable.
- **insane (5)**: Este modo es extremadamente agresivo y asume una red muy rápida y fiable. Aquí, la velocidad tiene prioridad sobre la precisión.

## Escaneo de SMTP
SMTP tiene dos directivas:
+ **Verify:** Al conectarte se ve si el usuario existe. Se suele desactivar.
+ **RCPT TO:** Especifica la dirección de correo del destinatario.

Para realizar pruebas de enumeración de usuarios, podemos utilizar:
```
smtp-user-enum -m vrfy/rcpt -U user.txt -T server.txt
```

## IP spoofing
Cuando antes enviábamos el SYN con una IP suplantada a la máquina que atacábamos, lo que estábamos haciendo era IP spoofing. Consiste en enviar paquetes con una IP falsa. Los routers se pueden configurar para rechazar los paquetes con una IP que no pertenezca a la red local. o que no cumplan ciertos requisitos de autencidad.

