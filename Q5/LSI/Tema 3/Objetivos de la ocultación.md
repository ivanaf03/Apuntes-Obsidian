[[Tema 3-Ocultación]]

## ¿Qué es la ocultación?
Es la práctica de ocultar información o sistemas para protegerlos de amenazas y ataques cibernéticos. También se conoce como "hiding". La ocultación puede utilizarse como una técnica de seguridad para dificultar o prevenir el acceso no autorizado a recursos críticos de una organización o sistema de información.

Por ejemplo, NAT no sirve para ocultar tu IP, ya que sales con la IP pública a internet. Por ejemplo, existen páginas web que lanzan scripts en JS que recogen la IP privada de tu máquina.

Los objetivos de la ocultación son:
+ Derecho a la privacidad y anonimato.
+ Prevenir que se conozcan datos como la IP o los hábitos de navegación.
+ Acceso a contenido sin censura.
+ Otros objetivos.

## Proxys
  Un proxy es un servidor intermedio que actúa como intermediario entre un usuario y el destino al que está accediendo. Cuando un usuario realiza una solicitud a través de un proxy, este reenvía la solicitud al servidor de destino en nombre del usuario y luego envía la respuesta del servidor de vuelta al usuario.

### Web-based proxies
Operan a través de una interfaz web. Los usuarios pueden acceder a ellos mediante un navegador sin necesidad de instalar software adicional. Ocultan la IP del usuario y cifra el tráfico entre el usuario y el proxy. 

### Open proxies
En este tipo de proxies el cliente debe configurar sus datos. Una vez hecho esto la navegación es transparente para el usuario. Pueden ser:
+ **Proxy HTTP/HTTPS:** Se ocupan del enrutamiento de solicitudes y respuestas HTTP entre clientes y servidores web. Este tipo de proxy se utiliza comúnmente para acceder a contenido web. Se pueden configurar con el comando (o añadiéndolo al .bashrc para que esta configuración sea persistente y se aplique cada vez que inicias una sesión de terminal):
```
export http_proxy=http://x.x.x.x:3128
```
+ **SOCKS:** protocolo de red que actúa como una puerta de enlace para las conexiones de red, facilitando la conexión a través de un servidor intermediario. Se configura en el fichero /etc/socks.conf:
```
deny [*=_userlist_] _dst_addr_ _dst_mask_ [_op_ _dst_port_] [: _shell_cmd_]

direct [*=_userlist_] _dst_addr_ _dst_mask_ [_op_ _dst_port]_ [: _shell_cmd_]

sockd [@=_serverlist_] [*=_userlist_] _dst_addr_ _dst_mask_ [_op_ _dst_port_] [: _shell_cmd_]
```

Pueden agregar información a las cabeceras de las solicitudes y respuestas. Algunos campos relevantes incluyen:
+ **REMOTE_ADDR:** indica la dirección IP remota, es decir, la dirección IP del cliente que realiza la solicitud a través del proxy SOCKS.
+ **X_FORWARDED_FOR:** puede contener una lista de direcciones IP que indica las direcciones por las que ha pasado la solicitud a través de proxies. Es importante tener cuidado con este campo, ya que puede revelar información sensible sobre la ruta que ha seguido la solicitud.

Los niveles de anonimato que pueden usar son:
+ **Ruidosos:** Estos proxies introducen información falsa en las cabeceras HTTP para confundir a los servidores y ocultar la identidad del usuario. Este método a menudo se asocia con proxies de baja calidad.
- **Transparentes:** Estos proxies no ocultan la dirección IP del cliente, pero pueden mejorar el rendimiento de la red mediante el almacenamiento en caché.
- **Alta Anonimicidad (Élite):** Estos proxies ofrecen el mayor grado de anonimato al ocultar completamente la dirección IP del cliente y no revelar que se está utilizando un proxy.

## VPN
Una VPN o Virtual Private Network es una tecnología que permite establecer una conexión segura y cifrada entre dos puntos en una red.

Hay proveedores comerciales de servicios VPN que ofrecen aplicaciones para establecer una conexión segura a través de sus servidores. Este software crea un túnel cifrado entre el equipo cliente y el servidor VPN del proveedor. El túnel creado es un conducto seguro a través del cual pasa todo el tráfico de datos entre el cliente y el servidor VPN. Este túnel está cifrado, lo que significa que los datos que viajan a través de Internet están protegidos de miradas indiscretas.

## Honeypots o honeys
Un honeypot es un recurso de red falso que se configura para atraer a posibles atacantes y simular vulnerabilidades o servicios en una red. Son una trampa diseñada para atraer a posibles atacantes o ciberdelincuentes con el fin de observar, estudiar y recopilar información sobre sus métodos y actividades.

## Borrado de ficheros
Aunque se borre un fichero totalmente, es fácil recuperarlo. Pero existen herramientas que si permiten borrarlos completamente de forma segura. Por ejemplo:
+ srm
+ shred
+ wipe

Estos comandos se basan en sobreescribir muchas veces el disco. Otra manera es con sfill, una herramienta que borra el espacio libre. Sswap hace lo mismo en las particiones de swap, smem para la memoria RAM, etc. Además hay que borrar además los logs, el historial de comandos...
