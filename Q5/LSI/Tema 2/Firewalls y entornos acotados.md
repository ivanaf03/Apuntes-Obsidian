[[Tema 2-Information gathering]]

### Traceroute
Generalmente la IP anterior a la de la organización es la IP del firewall. Pero muchas veces está el tráfico filtrado. Con las opciones -T y -U podemos enviar tráfico UDP o TCP.

### Firewalls
+ **Modo router:** es un router que a mayores realiza listas de acceso.
+ **NAT**: hace lo mismo que el anterior, pero a mayores traduce la intranet a direccionamiento público.
+ **Transparentes**: no tienen IPs, trabajan a nivel de MAC. Su ventaja es que a nivel de red nadie puede verlo. No se suelen montar por que son más caros y la gente no suele montarlos por falta de conocimiento, pereza, etc. Las herramientas que se usan son iptables y evetables.
+ **Firewall de nueva generación**: Se suelen montar varios, tienen anchos de banda muy potentes y se les pueden añadir plugins de seguridad.

### Metadatos
Los metadatos son los datos de información acerca de los ficheros. Algunas herramientas que se usan son Creepy, que recolecta fotos de internet y mapea los lugares donde han sido sacadas.

### Términos importantes
##### Spidering
Los buscadores lo hacen. Consiste en conectarse a múltiples servidores para enlazar páginas. subpáginas... hasta crear un árbol de búsqueda enorme. El spidering consiste en recorrer todo el árbol de un index.html de un servidor y descargarlo.

##### Crawlering
También lo hacen los buscadores. Es un análisis semántico de toda la información descargada.

##### Scrappering
Un ejemplo es, en Amazon, cuando accedes a un producto y se muestran los proveedores y sus precios. Consiste en recolectar información de otros lados y compararla con la recogida con el crawlering.

##### Hardening
Consiste en hacer los sistemas más seguros reconfigurando o securizando cosas. Lynis audit system es una herramienta que saca un archivo muy grande en base a un análisis completo de una máquina completa sobre consejos de seguridad. Por ejemplo:
+ Te dice que puedes instalar el libpam-tmp-dir, que añade seguridad a los ejecutables que utilizan las librerías de los procesos de autenticación.
+ Te dice que te puedes instalar apt-listbugs, que muestra las vulnerabilidades o bugs de un paquete.
+ Te dice que te puedes instalar needrestart, que recomienda reiniciar servicios por cambios en las librerías.
+ Te dice que te puedes instalar debscan, que analiza vulnerabilidades.
+ Te dice que te puedes instalar debsums, que comprueba hashes de paquetes instalados comparándolos con los de los paquetes originales.
+ Te dice que te puedes instalar fail2ban, que detecta ataques de password guessing.
+ PAE (Physical Adress Extension): Permite usar hasta 64 GB de RAM en arquitecturas de 32 bits.
+ DEP (Data Execution Prevention): Hace que el sistema no permita que la pila de datos ejecute nada.
+ Analiza fichero como el sudoers, el shadow, etc.
+ Recomienda instalar pam_cracklib, pwquality y pampasswdqc. Sirven para especificar políticas de contraseñas.
+ Cambiar el UMASK de 022 a 027. 
	+ 022: permisos default a rwxr_xr_x
	+ 027: permisos default a rwxr_x___
+ Bajar la variable de TMOUT (timeout) en el fichero /etc/profile o $HOME/.profile y en /etc/bash.bashrc o $HOME/.bashrc.
+ Es recomendable meter /home /var y /tmp en particiones separadas.
+ Deshabilitar la carga de módulos en el kernel (en /etc/sys/kernel). También se puede hacer con /etc/modprobe.d/blacklist.conf.
+ Da recomendaciones sobre servicios.
##### Sandbox
Un sandbox es un entorno acotado. Es similar a una pequeña virtual dentro del operativo, con sus librerías aisladas. Se puede hacer sandbox a un servicio, lo que hará que si lo hackean solo afecte a la zona aislada.

```
strace -e tarce=%file ssh
```

Este comando nos da todos los ficheros y librerías que utiliza el servicio ssh.

### Fichero /etc/security/limits.conf
Cada variable suele tener 2 límites: hard y soft. Por ejemplo:
+ Core: tamaño de los ficheros core
+ Tamaño máximo de memoria
+ Tamaño máximo de fichero
+ Número máximo de procesos
+ Número máximo de tiempo de CPU
+ ...

### Fichero /etc/pam-d/common-password
Permite especificar que función has se utiliza para calcular el hash de las contraseñas del fichero shadow. Además permite elegir los rounds. Los rounds son el número de veces que se hashea una contraseña para meterla en shadow. También se puede indicar los rounds por usuario, lo que complica más los ataques de password cracking.

##### Comando chage
Muestra cuando cada la contraseña de un usuario entre otras cosas. Por ejemplo, con "passwd -e user" podemos elegir una caducidad.

### Fichero /etc/shells
Contiene los diferentes intérpretes de comandos del sistema operativo.