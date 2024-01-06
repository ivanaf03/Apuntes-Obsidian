[[Tema 2-Information gathering]]

## Otras técnicas de information gathering
+ **Google dorking/Google hacking**: Se refiere a la técnica de utilizar motores de búsqueda como Google para encontrar información sensible o vulnerable en sitios web y servidores. Los "dorks" son consultas de búsqueda específicas que buscan revelar información que normalmente no debería ser accesible públicamente. Los hackers y profesionales de la seguridad informática utilizan esta técnica para identificar posibles puntos de entrada en sistemas, bases de datos mal configuradas, contraseñas filtradas y otros datos confidenciales. Algunos ejemplos de dorks incluyen buscar nombres de archivos, directorios o información específica de servidores web que los administradores pueden haber dejado accesibles inadvertidamente. Es importante destacar que el uso de Google hacking para fines maliciosos es ilegal y puede tener consecuencias legales graves.
+ **Footprinting**: es el proceso de recopilar información sobre un objetivo o sistema como parte de una evaluación de seguridad. Esta información puede incluir detalles sobre la infraestructura de red, direcciones IP, nombres de dominio, personas y empleados asociados, tecnologías utilizadas, servicios expuestos y más. El objetivo es obtener una comprensión completa del objetivo antes de intentar realizar un ataque o una prueba de penetración. El proceso de footprinting generalmente implica la recopilación de datos a partir de fuentes públicas, como motores de búsqueda, redes sociales, registros de dominio, registros WHOIS, escaneo de puertos y otros métodos de obtención de información no intrusivos. Esta información se utiliza luego para planificar ataques más específicos y dirigidos o para identificar vulnerabilidades potenciales en el sistema. Puede ser activo o pasivo.
+ **Spidering:** los buscadores lo hacen. Consiste en conectarse a múltiples servidores para enlazar páginas. subpáginas... hasta crear un árbol de búsqueda enorme. El spidering consiste en recorrer todo el árbol de un index.html de un servidor y descargarlo.
+ **Crawlering:** También lo hacen los buscadores. Es un análisis semántico de toda la información descargada.
+ **Scrappering:** Un ejemplo es, en Amazon, cuando accedes a un producto y se muestran los proveedores y sus precios. Consiste en recolectar información de otros lados y compararla con la recogida con el crawlering.
+ **Hardening:** Consiste en hacer los sistemas más seguros reconfigurando o securizando cosas. Lynis audit system es una herramienta que saca un archivo muy grande en base a un análisis completo de una máquina completa sobre consejos de seguridad. Por ejemplo:
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
		+ 027: permisos default a rwxr_x__
	+ Bajar la variable de TMOUT (timeout) en el fichero /etc/profile o $HOME/.profile y en /etc/bash.bashrc o $HOME/.bashrc.
	+ Es recomendable meter /home /var y /tmp en particiones separadas.
	+ Deshabilitar la carga de módulos en el kernel (en /etc/sys/kernel). También se puede hacer con /etc/modprobe.d/blacklist.conf.
	+ Da recomendaciones sobre servicios.
+ **Information gathering con metadatos:** Los metadatos son los datos de información acerca de los ficheros. Algunas herramientas que se usan son Creepy, que recolecta fotos de internet y mapea los lugares donde han sido sacadas.