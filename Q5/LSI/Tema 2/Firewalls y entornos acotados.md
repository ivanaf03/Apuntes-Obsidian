[[Tema 2-Information gathering]]

## Firewalls
+ **Modo router:** es un router que a mayores realiza listas de acceso.
+ **NAT**: hace lo mismo que el anterior, pero a mayores traduce la intranet a direccionamiento público.
+ **Transparentes**: no tienen IPs, trabajan a nivel de MAC. Su ventaja es que a nivel de red nadie puede verlo. No se suelen montar por que son más caros y la gente no suele montarlos por falta de conocimiento, pereza, etc. Las herramientas que se usan son iptables y evetables.
+ **Firewall de nueva generación**: Se suelen montar varios, tienen anchos de banda muy potentes y se les pueden añadir plugins de seguridad.

Generalmente la IP anterior a la del router de la organización es la IP del firewall. Pero muchas veces está el tráfico ICMP filtrado. Con traceroute y las opciones -T y -U podemos enviar tráfico UDP o TCP.

## Sandbox y restricciones
Un sandbox es un entorno acotado. Es similar a una pequeña máquina virtual dentro del operativo, con sus librerías aisladas. Se puede hacer sandbox a un servicio, lo que hará que si lo hackean solo afecte a la zona aislada.

Este comando nos da todos los ficheros y librerías que utiliza el servicio ssh:
```
strace -e trace=file ssh
```

Otras formas de acotar los accesos es tocando ciertos parámetros en ficheros.

### Fichero /etc/security/limits.conf
Cada variable suele tener 2 límites: hard y soft. Algunos ejemplos son:
+ Tamaño de los ficheros core
+ Tamaño máximo de memoria
+ Tamaño máximo de fichero
+ Número máximo de procesos
+ Número máximo de tiempo de CPU

### Fichero /etc/pam-d/common-password
Permite especificar que función hash se utiliza para calcular el hash de las contraseñas del fichero shadow. Además permite elegir los rounds. Los rounds son el número de veces que se hashea una contraseña para meterla en shadow. También se puede indicar los rounds por usuario, lo que complica más los ataques de password cracking.

El comando chage muestra cuando caduca la contraseña de un usuario entre otras cosas. Por ejemplo para asignar una caducidad:
```
passwd -e user
```

Podemos ver la caducidad con:
```
chage -l user
```

### Fichero /etc/shells
Contiene la lista de intérpretes de comandos permitidos en el sistema. Es utilizado para definir qué shells están habilitados para los usuarios.