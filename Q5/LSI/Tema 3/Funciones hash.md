[[Tema 3-Ocultación]]

## Herramientas de hashing
+ hash-identify
+ hashid py
+ findanyhash

## Ataques
Password guessing: ataques contra los servicios de tipos login y passwors probando password continuamente. Son muy lentos, por eso hay que crear buenos diccionarios. Suelen dejar registros en los logs del sistema. Los captchas sirven para frenar los ataques de password guessing. Otra forma es con filtros de IP, por ejemplo, limitando los intentos que puedes hacer desde determinada IP. Normalmente los sistemas tienen un número de bloqueos y las herramientas de password guessing suelen evitarlos. Una manera de hacerlo es probando en vez de usuario->n passwords, n usuarios->password.

#### Herramientas
Medusa:
```
medusa -M ssh -q
medusa -h 10.11.48.x -u lsi -P p.txt - ssh -f
```

#### Protección
Fail2ban: detecta ataques de password guessing.
OSSEC (HIPS): es un sistema de prevención de intrusiones a nivel de host. 

## Wget
Permite descargar una página web usando spidering.
```
wget -r -K http://example.com
```

## Cómo proteger el grub
```
grub-mkpasswd-pbkdf2

Escribir en /etc/grub.d/40_custom:
	set superuser=root
	password-pbkdf2 root (hash generado por el comando anterior)

update grub
```

## Krack attack
Permite atacar al tráfico en una conexión wifi. Se basa en bloquear el mensaje 4 del handshaking para hacer que el cliente reinstale la contraseña. Se hace con un MITM.

#### WPA3
Es el último estándar de wifi. Salió para evitar estos ataques, en 2018. Cambia la forma de realizar el handshake. También la longitud clave de cifrado, cifra las tramas de gestión. Existen nuevos ataques como dragonblood contra WPA3.

## Borrado de ficheros
Aunque se borre un fichero totalmente, es fácil recuperarlo. Pero existen herramientas que si permiten borrarlos completamente de forma segura. Por ejemplo:
+ srm
+ shred
+ wipe

Estos comandos se basan en sobreescribir muchas veces el disco. Otra manera es con sfill, una herramienta que borra el espacio libre. Sswap hace lo mismo en las particiones de swap, smem para la memoria RAM, etc. Además hay que borrar además los logs, el historial de comandos...

## DNS leaks
Son situaciones en las que la información relacionada con las solicitudes de nombres de dominio (DNS) de un usuario se filtra o se revela a terceros no autorizados, a pesar de usar una red VPN (Virtual Private Network) o proxy para proteger su privacidad y anonimato en línea. Estas filtraciones pueden comprometer la privacidad y el anonimato del usuario, ya que los registros de DNS pueden revelar qué sitios web está visitando y, en algunos casos, incluso su ubicación geográfica.

## Conexiones automáticas
Ejemplo: el ordenador emite tramas probe request con los wifis que se tienen automáticamente memorizados. Es posible esnifarlas. En wigle.net, poniendo la MAC del router, podemos sacar hasta la casa de la persona. Se pueden configurar los puntos de acceso para que no emitan beacons.

#### Ejemplos de redes de anonimatos
+ freewet
+ izp
+ top
+ jap
+ morphmix
+ retroshare
