[[Tema 3-Ocultación]]

### Definición
Es la práctica de ocultar información o sistemas para protegerlos de amenazas y ataques cibernéticos. También se conoce como "hiding". La ocultación puede utilizarse como una técnica de seguridad para dificultar o prevenir el acceso no autorizado a recursos críticos de una organización o sistema de información.

Por ejemplo, NAT no sirve para ocultar tu IP, ya que sales con la IP pública a internet. Por ejemplo, existen páginas web que lanzan scripts en JS que recogen la IP privada de tu máquina.

### Proxys
Pueden ser:
+ HTTP: enrutan solicitudes y respuestas HTTP entre clientes y servidores web.
+ SOCKs: permite que un cliente, como un navegador web o una aplicación, solicite recursos o servicios a través de un servidor proxy.

Los proxys tiene un campo (REMOTE_ADDR) donde va la IP remota. Además tienen otro campo (X_FORWARDED_FOR) con el que hay que tener cuidado, ya que muestra todas las IPs de los proxys por los que se fue pasando.