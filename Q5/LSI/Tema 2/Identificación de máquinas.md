[[Tema 2-Information gathering]]

### Máquinas en una organización
Debemos identificar en una organización todo tipo de máquinas que existan: ordenadores, firewalls, servidores, etc. Una muy mala práctica es meter los routers, por ejemplo, en las primeras direcciones IP de la organización. Se utilizan herramientas como:
+ Ping
+ Traceroute

Uno de los problemas del traceroute es que muchas veces filtran el tráfico. Ocurre cuando salen asteriscos.

### DNS
Los DNS pueden trabajar de dos formas: 
+ De forma directa: nombre--->ip
+ De forma inversa: ip--------->nombre

Trabajan en varios niveles. Si le pides una IP al servidor DNS y la tiene en caché, te la devuelve automáticamente. En cualquier otro caso se va a otros niveles hasta que encuentra la IP que se solicita.

Pueden ser: 
+ Primarios: 
+ Secundarios

A nivel funcional realizan lo mismo. A nivel administrador, el servidor primario se tiene que mantener, es decir, guardar en su base de datos toda la información. Los secundarios hacen transferencias de zona, es decir, se conectan cada x tiempo a los primarios y transfieren toda su base de datos.

Herramientas:
+ nslookup
+ dig
+ dnsenum
+ dnsrecon
+ dnsmap

### Caché snooping
Si el servidor DNS te da directamente la página, eso significa que ya estaba en caché. Por tanto, alguien ya había entrado ahí antes. El comando
```
dnsrecon -t snoop -n x.x.xservdns -D file
```
se utiliza para realizar una búsqueda exhaustiva en un servidor DNS específico (especificado por la dirección IP o el nombre "x.x.xservdns") utilizando una lista de nombres de dominio o direcciones IP contenidas en un archivo de entrada llamado "file". El objetivo es recopilar información detallada sobre los registros DNS asociados con los nombres de dominio o direcciones IP proporcionados en el archivo.

La recursión en DNS se refiere a la capacidad de un servidor DNS para buscar información en otros servidores DNS si no tiene la respuesta a una consulta en su propia base de datos. Esto es común en la resolución de nombres de dominio en Internet, donde los servidores DNS pueden buscar información en otros servidores si no tienen la respuesta en caché.

El comando "dnsrecon" generalmente se utiliza para realizar búsquedas exhaustivas en un servidor DNS específico, como lo indica la opción "-t snoop". Esto significa que intentará enumerar todos los registros DNS disponibles en el servidor DNS objetivo, pero no necesariamente ejecutará consultas recursivas en otros servidores DNS. En lugar de eso, se enfoca en recopilar información del servidor DNS específico que especifiques con la opción "-n".

### Siguiente paso
Una vez localizadas las máquinas, los siguientes pasos serían:
+ Comprobar los puertos
+ Fingerprinting del SO
+ Fingerprinting de puertos
+ Mapeo
+ Localización de vulnerabilidades con openvos o nessus

Herramientas de explotación de vulnerabilidades:
+ Shodan
+ TheFatRat
+ Metasploit
+ Cobal strike