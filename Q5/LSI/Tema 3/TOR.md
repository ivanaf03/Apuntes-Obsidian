[[Tema 3-Ocultación]]

### Red Tor
La red Tor son una serie de directorios por la que circulan los nodos, El objetivo es routear las conexiones a través de nodos para conseguir anonimato. Los nodos no son más que máquinas configuradas con ciertos anchos de banda. 

Tor va montado sobre un proxy, que adapta la paquetería a la red Tor. Al establecer una conexión se eligen una serie de nodos (mínimo 3). Establece con cada uno de ellos una clave de sesión. De ahí viene el nombre de los onion, un paquete funciona como una cebolla, se cifran los nodos del más alejado (interno) al menos y una vez van llevando al respectivo nodo se van descifrando como si fueran capas de una cebolla.

Dentro de la red Tor existen servicios ocultos. Son los dominios .onion (suelen ser dominios de 56 caracteres en base 32) que funcionan como un servidor web. Solo son accesibles a través de Tor. Son así para que sea sencillo tracearlos por fuerza bruta.

Uno de sus mayores problemas es el rendimiento, ping y ancho de banda. En la última versión empieza a añadir protocolos de control de congestión.

## TAILs
Tails es una distribución de Linux diseñada para proporcionar privacidad y anonimato en línea. El nombre "Tails" es un acrónimo de "The Amnesic Incognito Live System" (Sistema en Vivo Amnésico e Incógnito), y se enfoca en proteger la privacidad de los usuarios y ayudarles a mantenerse anónimos en Internet. Tails se ejecuta desde una unidad USB o un DVD sin necesidad de instalación en el disco duro de una computadora, lo que hace que sea fácil de usar sin dejar rastros en el sistema en el que se ejecuta.

Tails incluye una variedad de herramientas y aplicaciones diseñadas para mejorar la seguridad y el anonimato en línea. Por ejemplo, Tor.

## Deep web
La Deep Web es una parte de Internet que no está indexada por los motores de búsqueda convencionales como Google, Bing o Yahoo. A diferencia de la "Surface Web", que es la parte de Internet a la que se puede acceder a través de motores de búsqueda y enlaces directos, la Deep Web es una parte oculta y no se puede encontrar fácilmente. Esta parte de Internet no está necesariamente relacionada con actividades ilegales ni es inaccesible para usuarios legítimos; simplemente no se encuentra a través de búsquedas en motores de búsqueda comunes.

La Deep Web incluye contenido que es dinámico y protegido por contraseña, como bases de datos privadas, sistemas de gestión de contenido detrás de muros de inicio de sesión, cuentas de correo electrónico privadas y más. También abarca contenido que no está en formato HTML estándar, como archivos PDF, documentos de Word, videos y otros tipos de archivos que no se indexan automáticamente.

No obstante, la Deep Web no debe confundirse con la "Dark Web". La Dark Web es una parte más pequeña y específica de la Deep Web que está deliberadamente oculta y requiere software y configuraciones especiales para acceder. La Dark Web a menudo se asocia con actividades ilegales y mercados clandestinos en línea, donde se pueden comprar y vender bienes ilegales como drogas, armas y servicios de hacking.

## Algoritmos de nodos Tor
#### Tor Vegas
Se encarga de ajustar el tamaño de cola de los nodos. El nombre viene del protocolo TCP Vegas, que hacía ajustes dinámicos del tamaño de ventana. 

#### Tor Nola
Es un algoritmo que estima la latencia que habrá. Con esa información modifican los tamaños de ventana.

## ATM
"Modo de Transferencia Asíncrona" (Asynchronous Transfer Mode en inglés), es una tecnología de conmutación de paquetes que se utiliza en el ámbito de las redes de comunicación. Una de las características distintivas de ATM es que utiliza una tasa de transferencia constante para la transmisión de datos. Esto significa que los datos se dividen en celdas de 53 bytes (en lugar de paquetes variables como en Ethernet) y se transmiten a una velocidad constante, lo que garantiza una calidad de servicio (QoS) predecible y adecuada para aplicaciones sensibles al tiempo, como la transmisión de voz y video. Las celdas se conmutan a través de la red en lugar de paquetes completos.

### Saltarse un firewall
Se cambia en el fichero de configuración del ssh (/etc/sshd.conf) el puerto del 22 al 443. Ahora con ssh -p 443 podemos conectarnos a ese servidor ssh. Un firewall que si haga filtrado de paquetes no lo permitiría. Ahora el puerto al que te conectas con http://localhost:puerto, estarías reforwardeado al puerto de la máquina a la que te has conectado.

```
ssh -l user -L puerto:x.x.x.x:2128
```

Si puerto= 0.0.0.0, podremos servir de router y otra máquina puede conectarse a la nuestra para conectarse a la remota.

```
ssh -p 443 -fN -D 0.0.0.0:1080 user@x.x.x.x # forwardeo dinámico, proxy sock para saltarse un firewall (suele ser necesario un servicio de dns dinámico si no tenemos la misma IP siempre)
```

Otra herramienta para saltar proxys es corkscrew. Permite mediante ssh y forwardeo de puertos saltarese un proxy. 

El port knocking nos permite mediante una secuencia de peticiones tirar el servicio y mediante cierta secuencia de comandos permite levantarlo otra vez. Se monta en el fichero /etc/knockd.conf, donde por ejemplo tenemos:
```
(open ssh)
sequence=7001, 7015, 9000
tcpflag=SYN
command=systemctl start ssh; /etc/sysconfig/iptables (completar)
...
(close ssh)
sequence=7000, 7018, 9003
```

El web knocking es una técnica de seguridad que se utiliza para proteger los servicios en línea, como servidores web, bases de datos y otros servicios de red, al ocultar sus puertos y hacer que sean inaccesibles hasta que un usuario autorizado realice una serie específica de solicitudes a través de la web. Esta técnica se basa en la premisa de que los servicios no estarán disponibles a menos que el usuario realice una secuencia predefinida de "toques" o solicitudes a través de la web. Una vez que se completa esta secuencia de solicitudes, los servicios se desbloquean y se vuelven accesibles para el usuario autorizado.