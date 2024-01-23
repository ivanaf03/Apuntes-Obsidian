[[Tema 3-Ocultación]]

## ATM
"Modo de Transferencia Asíncrona" (Asynchronous Transfer Mode en inglés), es una tecnología de conmutación de paquetes que se utiliza en el ámbito de las redes de comunicación. Una de las características distintivas de ATM es que utiliza una tasa de transferencia constante para la transmisión de datos. Esto significa que los datos se dividen en celdas de 53 bytes (en lugar de paquetes variables como en Ethernet) y se transmiten a una velocidad constante, lo que garantiza una calidad de servicio (QoS) predecible y adecuada para aplicaciones sensibles al tiempo, como la transmisión de voz y vídeo. Las celdas se conmutan a través de la red en lugar de paquetes completos.

## Handshake entre una máquina y un punto de acceso
Cuando un dispositivo se conecta a un punto de acceso Wi-Fi, se realiza un proceso de autenticación y establecimiento de claves conocido como handshake. Durante este proceso, se generan claves que serán utilizadas para cifrar las comunicaciones entre el dispositivo y el punto de acceso.

La PTK es una clave de cifrado temporal que se genera durante el handshake y se utiliza para asegurar la comunicación entre un dispositivo y un punto de acceso. Se construye como:

$$PTK=PMK-ANOUNCE+SNOUNCE+MAC(acceso)+MAC(dispositivo)$$

- **PMK (Pairwise Master Key):** Es una clave derivada de la autenticación de la contraseña (pre-shared key o PSK) compartida entre el dispositivo y el punto de acceso.
- **ANOUNCE y SNOUNCE:** Son números aleatorios generados por el dispositivo y el punto de acceso durante el proceso de handshake.

El comando "aircrack-ng -w diccionario captura" realiza un ataque de fuerza bruta contra una captura de handshake previamente grabada.

### Otras herramientas
+ **Aircrack-ng:** Es una suite de herramientas que incluye:
	+ **airmon-ng:** Se utiliza para poner una tarjeta de red inalámbrica en modo de monitorización (modo promiscuo), lo que permite la captura de todo el tráfico de una red inalámbrica, incluso los paquetes que no están destinados a la propia tarjeta de red.
	+ **airodump-ng:** Permite capturar paquetes de datos, paquetes de autenticación y paquetes de asociación en una red inalámbrica. Es útil para la recolección de información sobre redes Wi-Fi.
	+ **aircrack-ng:** Utilizado para romper las claves de cifrado de redes Wi-Fi. Puede utilizar ataques de fuerza bruta y diccionario para descifrar contraseñas WEP y WPA/WPA2.
	+ **airplay-ng:**  Se utiliza para generar y enviar tráfico de red inalámbrica a una red Wi-Fi específica. Puede ser útil en ataques de inyección de paquetes y para obtener información adicional sobre la red.
+ **wifite:** es una herramienta de código abierto diseñada para auditar y penetrar redes inalámbricas. Su nombre es una combinación de "WiFi" y "Fight" (lucha), ya que se utiliza para "luchar" contra redes inalámbricas aseguradas. WiFite simplifica y automatiza muchas de las tareas asociadas con la auditoría de seguridad de redes Wi-Fi, como la detección, la captura de contraseñas y la selección de ataques.
+ **cewl:** hace spidering analizando el contenido de una página web o un archivo de texto y extrae palabras clave relevantes. Estas palabras clave son aquellas que podrían ser útiles para realizar ataques de ingeniería social, como ataques de suplantación de identidad o ataques de fuerza bruta en contraseñas.
+ **The Harvester:** herramienta para la obtención de información en fuentes abiertas. Para ello, utiliza métodos pasivos para, de esta manera, conseguir la información que estamos buscando sin interactuar directamente con el objetivo final (dominio, persona, etc…) a través de los diferentes motores de los principales buscadores y servicios utilizados, o si lo preferimos de forma activa haciendo fuerza bruta, resoluciones inversas, etc…
+ **mutator:** generación de diccionarios con mutaciones de palabras.
+ **fluxion:** suplanta un punto de acceso. Lo que hace es que cuando alguien se conecta a tu equipo envía una página donde pide la clave.

## Wi-Fi Protected Setup
Es un estándar de seguridad para redes Wi-Fi que se creó con el objetivo de simplificar la configuración de conexiones seguras entre dispositivos y puntos de acceso Wi-Fi.

Hubo un ataque muy exitoso al protocolo WPS se debía a un proceso de autenticación inseguro y a la falta de medidas de seguridad en la implementación del protocolo:
1. **Estructura del PIN de WPS**: El PIN de WPS consta de 8 dígitos. Se divide en dos partes: la primera parte tiene 4 dígitos, y la segunda parte tiene 3 dígitos, con un dígito de control al final. Esto resulta en un total de 10^7 posibles combinaciones.
2. **Falta de Bloqueo de Intentos**: La vulnerabilidad principal radicaba en la falta de bloqueo o retraso después de un número determinado de intentos fallidos de PIN. A diferencia de otros sistemas de seguridad que bloquean a un usuario después de un número de intentos fallidos, WPS no aplicaba ningún bloqueo o medida de seguridad similar.
3. **Ataque de Fuerza Bruta Acelerado**: Los atacantes podían utilizar herramientas automatizadas para realizar ataques de fuerza bruta. Podían probar todas las combinaciones posibles (10^7) en poco tiempo debido a la falta de bloqueo de intentos. Esto permitía que los atacantes intentaran cada combinación en rápida sucesión.
4. **Identificación Rápida del PIN Válido**: Debido a la falta de bloqueo, los atacantes podían identificar rápidamente el PIN válido (generalmente en un número mucho menor de intentos de lo esperado) y, una vez que tenían el PIN válido, podían descubrir la clave de seguridad de la red.

## Saltarse un firewall
Se cambia en el fichero de configuración del ssh (/etc/sshd.conf) el puerto del 22 al 443. Ahora con ssh -p 443 podemos conectarnos a ese servidor ssh. Un firewall que si haga filtrado de paquetes no lo permitiría. Ahora el puerto al que te conectas con http://localhost:puerto, estarías reforwardeado al puerto de la máquina a la que te has conectado.

```
ssh -l user -L x.x.x.x:2128
```

Si x.x.x.x= 0.0.0.0, podremos servir de router y otra máquina puede conectarse a la nuestra para conectarse a la remota.

```
ssh -p 443 -fN -D 0.0.0.0:1080 user@x.x.x.x # forwardeo dinámico, proxy sock para saltarse un firewall (suele ser necesario un servicio de dns dinámico si no tenemos la misma IP siempre)
```

Otra herramienta para saltar proxys es corkscrew. Permite mediante ssh y forwardeo de puertos saltarse un proxy. 

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