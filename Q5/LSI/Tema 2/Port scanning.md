[[Tema 2-Information gathering]]

### Puertos
Para escanear máquinas se lanzan peticiones a puertos y podemos ver si están abiertos, cerrados, filtrados, etc. Un firewall puede ser:
+ Sin control de estado: suele trabajar en capas 3 y 4 y decide que deja o no deja conectarse, filtrando el tráfico
+ Con control de estado: hace lo mismo, pero verificando que se sigue el handshaking de apertura y cierre (envío de syn, recepción de ack+syn...) . Para escanear un firewall de este tipo tenemos que usar el flag syn.

##### Idle scan
Es una técnica de escaneo de puertos utilizada en ciberseguridad y pruebas de penetración para determinar si un puerto específico en un sistema objetivo está abierto o cerrado, sin alertar directamente al sistema objetivo ni dejar rastros en los registros del sistema. Esta técnica se basa en la explotación de la propiedad de los sistemas TCP/IP de mantener la coherencia en la numeración de secuencia de los paquetes y en la utilización de sistemas intermedios (como un firewall o un host zombie) para llevar a cabo el escaneo.

Se hace con:
```
nmap -p0 -p 80 -sI x.x.x.x www.maquina.com
```

Lo que hace en enviar un syn-ack a la máquina zombie, a lo que responderá con un rst. Luego se enví un syn con la IP del zombie. Si el puerto está abierto el zombie recibe un syn-ack. A lo que responde con un rst. Luego se envía un syn ack al zombie, a lo que responde con otro rst. Si el puerto está abierto, el ip id se habrá aumentado en 2. Los kernels modernos ya no utilizan ip id secuenciales para evitar esto.

### IP spoofing
Cuando antes enviábamos el syn con una IP suplantada a la máquina que atacábamos, lo que estábamos haciendo era IP spoofing. Consiste en enviar paquetes con una IP falsa. Los routers se pueden configurar para rechazar los paquetes con una IP que no pertenezca a la red.
