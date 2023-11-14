[[Tema 3-Ocultación]]

### Definición
Es la práctica de ocultar información o sistemas para protegerlos de amenazas y ataques cibernéticos. También se conoce como "hiding". La ocultación puede utilizarse como una técnica de seguridad para dificultar o prevenir el acceso no autorizado a recursos críticos de una organización o sistema de información.

Por ejemplo, NAT no sirve para ocultar tu IP, ya que sales con la IP pública a internet. Por ejemplo, existen páginas web que lanzan scripts en JS que recogen la IP privada de tu máquina.

### Proxys
Pueden ser:
+ HTTP: enrutan solicitudes y respuestas HTTP entre clientes y servidores web.
Pueden ser:
+ ruidosos: meten en las cabeceras información falsa
+ transparentes
+ alta anonimicidad
+ anónimos

```
export http_proxy=http://x.x.x.x:3128
```
Se utiliza para configurar un proxy HTTP en un entorno de línea de comandos o en una sesión de terminal. Esto se podría añadir al bashrc.

+ SOCKs: permite que un cliente, como un navegador web o una aplicación, solicite recursos o servicios a través de un servidor proxy.
En el archivo /etc/socks.conf se ponen como direct las ips de entrada directa y el resto sockd x.x.x.x 0.0.0.0 0.0.0.0, donde x.x.x.x es una ip don de hay montado un proxy sock.

Los proxys tiene un campo (REMOTE_ADDR) donde va la IP remota. Además tienen otro campo (X_FORWARDED_FOR) con el que hay que tener cuidado, ya que muestra todas las IPs de los proxys por los que se fue pasando.


## Honeys
Es una trampa diseñada para atraer a posibles atacantes o ciberdelincuentes con el fin de observar, estudiar y recopilar información sobre sus métodos y actividades. Los honeypots son herramientas de seguridad utilizadas para detectar y analizar amenazas en la red y proteger sistemas informáticos.

## Herramientas contra wifi
airmon-ng: se utiliza para tareas como poner una tarjeta de red inalámbrica en modo de monitorización (modo promiscuo), lo que permite capturar todo el tráfico de una red inalámbrica, incluyendo los paquetes que no están destinados a la propia tarjeta de red

airodump-ng: permite capturar paquetes de datos, paquetes de autenticación y paquetes de asociación en una red inalámbrica.

aircrack-ng: se utiliza para romper las claves de cifrado de redes Wi-Fi. Puede utilizar ataques de fuerza bruta y diccionario para descifrar contraseñas WEP y WPA/WPA2.

airplay-ng: se utiliza para generar y enviar tráfico de red inalámbrica a una red Wi-Fi específica, lo que puede ser útil en ataques de inyección de paquetes y en la obtención de información adicional sobre la red.

wifite: es una herramienta de código abierto diseñada para auditar y penetrar redes inalámbricas. Su nombre es una combinación de "WiFi" y "Fight" (lucha), ya que se utiliza para "luchar" contra redes inalámbricas aseguradas. WiFite simplifica y automatiza muchas de las tareas asociadas con la auditoría de seguridad de redes Wi-Fi, como la detección, la captura de contraseñas y la selección de ataques.

cewl: hace spidering analizando el contenido de una página web o un archivo de texto y extrae palabras clave relevantes. Estas palabras clave son aquellas que podrían ser útiles para realizar ataques de ingeniería social, como ataques de suplantación de identidad o ataques de fuerza bruta en contraseñas.

thchardbester

mutator

crunk

fluxion: suplanta un punto de acceso. Lo que hace es que cuando alguien se conecta a tu equipo envía una página donde pide la clave.

hashcat: herramienta de crackeo de hashes. Otras son cain&abel, john. El fichero /etc/shadow esta formado por user: \$función_hash\$ SALT(entre 8 y 16 caracteres): password hasheado salteado: otros parámetros

El SALT es un valor aleatorio que se utiliza como parte de la operación de hashing (resumen) de contraseñas almacenadas en el archivo "shadow". Garantiza que, aunque dos usuarios tengan la misma contraseña, sus valores de hash en el archivo "shadow" serán diferentes debido al SALT único. Esto dificulta la obtención de contraseñas a partir de tablas de hash precalculadas (ataques de tablas arco iris) y hace que los ataques de fuerza bruta sean más costosos y lentos, ya que el atacante debe probar todas las combinaciones posibles con el SALT correcto.

## Handshake entre una máquina y un punto de acceso
PTK=PMK-ANOUNCE+SNOUNCE+MAC(acceso)+MAC(dispositivo)

El comando aironplay-ng -w diccionario captura hace fuerza bruta 

## WPS
Es un estándar de seguridad para redes Wi-Fi que se creó con el objetivo de simplificar la configuración de conexiones seguras entre dispositivos y puntos de acceso Wi-Fi.
El ataque exitoso al protocolo WPS (Wi-Fi Protected Setup) se debía a un proceso de autenticación inseguro y a la falta de medidas de seguridad en la implementación del protocolo. A continuación, te explicaré paso a paso por qué este ataque era rápido:

1. **Estructura del PIN de WPS**: El PIN de WPS consta de 8 dígitos. Se divide en dos partes: la primera parte tiene 4 dígitos, y la segunda parte tiene 3 dígitos, con un dígito de control al final. Esto resulta en un total de 10^7 posibles combinaciones.
    
2. **Falta de Bloqueo de Intentos**: La vulnerabilidad principal radicaba en la falta de bloqueo o retraso después de un número determinado de intentos fallidos de PIN. A diferencia de otros sistemas de seguridad que bloquean a un usuario después de un número de intentos fallidos, WPS no aplicaba ningún bloqueo o medida de seguridad similar.
    
3. **Ataque de Fuerza Bruta Acelerado**: Los atacantes podían utilizar herramientas automatizadas para realizar ataques de fuerza bruta. Podían probar todas las combinaciones posibles (10^7) en poco tiempo debido a la falta de bloqueo de intentos. Esto permitía que los atacantes intentaran cada combinación en rápida sucesión.
    
4. **Identificación Rápida del PIN Válido**: Debido a la falta de bloqueo, los atacantes podían identificar rápidamente el PIN válido (generalmente en un número mucho menor de intentos de lo esperado) y, una vez que tenían el PIN válido, podían descubrir la clave de seguridad de la red.

