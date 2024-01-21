[[Tema 3-Ocultación]]

## ¿Qué son las redes de anonimato?
Son redes que permiten a los usuarios comunicarse de forma anónima. Usan cifrado por capas (onion routing). Son lentas porque los usuarios comparten sus recursos con la red. Algunos ejemplos son:
+ freenet
+ i2p
+ tor
+ jap
+ morphmix
+ retroshare

### Red Tor
Es una herramienta gratuita cuyo objetivo es que la gente pueda usar Internet de forma anónima (anonimato de origen). Tor protege al usuario haciendo rebotar sus comunicaciones sobre una red distribuida de relays (también llamados Onion Routers) ejecutados por voluntarios de todo el mundo. 

La red se compone por:
+ **Onion Routers:** encargados de enrutar el tráfico a través de la red y proporcionar anonimato al ocultar la identidad y ubicación del usuario. Cualquier usuario puede optar por convertirse en un nodo en la red Tor. Estos nodos ayudan a enrutar el tráfico de manera anónima a través de comunicación TLS.
+ **Onion Proxys:** usuarios finales de la red Tor. Al establecer una conexión se eligen una serie de nodos (mínimo 3). Establece con cada uno de ellos una clave de sesión. De ahí viene el nombre de los onion, un paquete funciona como una cebolla, se cifran los nodos del más alejado (interno) al menos y una vez van llevando al respectivo nodo se van descifrando como si fueran capas de una cebolla.

Dentro de la red Tor existen servicios ocultos. Son los dominios .onion (suelen ser dominios de 56 caracteres en base 32) que funcionan como un servidor web. Solo son accesibles a través de Tor. Son así para que no sea sencillo tracearlos por fuerza bruta. Usando "rendezvous points" (puntos de encuentro), otros usuarios de Tor se pueden conectar a estos servicios ocultos, sin que ninguno de los dos conozca la identidad del otro

Uno de sus mayores problemas es el rendimiento, ping y ancho de banda. En la última versión empieza a añadir protocolos de control de congestión.

### Algoritmos de nodos Tor
+ **Tor Vegas:** se encarga de ajustar el tamaño de cola de los nodos. El nombre viene del protocolo TCP Vegas, que hacía ajustes dinámicos del tamaño de ventana. 
+ **Tor Nola:** es un algoritmo que estima la latencia que habrá. Con esa información modifican los tamaños de ventana.

### Funcionamiento de la red Tor
![[Tor 1.png]]
![[Tor 2.png]]
![[Tor 3.png]]
![[Tor 4.png]]
![[Tor 5.png]]

## TAILs
Tails es una distribución de Linux diseñada para proporcionar privacidad y anonimato en línea. El nombre "Tails" es un acrónimo de "The Amnesic Incognito Live System" (Sistema en Vivo Amnésico e Incógnito), y se enfoca en proteger la privacidad de los usuarios y ayudarles a mantenerse anónimos en Internet. Tails se ejecuta desde una unidad USB o un DVD sin necesidad de instalación en el disco duro de una computadora, lo que hace que sea fácil de usar sin dejar rastros en el sistema en el que se ejecuta.

Tails incluye una variedad de herramientas y aplicaciones diseñadas para mejorar la seguridad y el anonimato en línea. Por ejemplo, Tor.

## Deep web
La Deep Web es una parte de Internet que no está indexada por los motores de búsqueda convencionales como Google, Bing o Yahoo. A diferencia de la "Surface Web", que es la parte de Internet a la que se puede acceder a través de motores de búsqueda y enlaces directos, la Deep Web es una parte oculta y no se puede encontrar fácilmente. Esta parte de Internet no está necesariamente relacionada con actividades ilegales ni es inaccesible para usuarios legítimos; simplemente no se encuentra a través de búsquedas en motores de búsqueda comunes.

La Deep Web incluye contenido que es dinámico y protegido por contraseña, como bases de datos privadas, sistemas de gestión de contenido detrás de muros de inicio de sesión, cuentas de correo electrónico privadas y más. También abarca contenido que no está en formato HTML estándar, como archivos PDF, documentos de Word, videos y otros tipos de archivos que no se indexan automáticamente.

No obstante, la Deep Web no debe confundirse con la "Dark Web". La Dark Web es una parte más pequeña y específica de la Deep Web que está deliberadamente oculta y requiere software y configuraciones especiales para acceder. La Dark Web a menudo se asocia con actividades ilegales y mercados clandestinos en línea, donde se pueden comprar y vender bienes ilegales como drogas, armas y servicios de hacking.





