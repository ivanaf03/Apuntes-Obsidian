[[Tema 10-Virtualización de servidores]]

## Fundamentos de la computación
En los 80 los mainframe comenzaron a evolucionar a redes mucho más pequeñas hasta llegar a las LAN que tenemos hoy en día. 

Las aplicaciones y los sistemas operativos son el software que se ejecuta en sistemas cliente y servidor. El software se almacena en dispositivos de almacenamiento no volátil, como discos duros o SSDs. Para ejecutar el software, debe cargarse desde el almacenamiento en la memoria, o RAM. Los procesadores (CPU) simulan ejecutar muchas cosas a la vez al alternar rápidamente entre tareas.

Los servidores son sistemas así, pero más potentes y costosos. Tendían a correr una sola aplicación por servidor.  Se hacía así para evitar problemas de dependencias, de robo de recursos...

Hace unos años, se empezaron a aislar las aplicaciones en un solo servidor. Esto evolucionó separando el disco en cabinas. Esto era el estándar de los CPD hasta 2015/16.

Sin embargo, las cabinas son muy caras y difíciles de gestionar. De ahí surge la hiperconvergencia. Consiste en volver a meter el disco en los servidores, pero virtualizando el almacenamiento. Este software convierte todos los discos de los servidores en una simulación de una cabina. Además los datos están redundados en más de un nodo.

## Virtualización, emulación y paravirtualización
Las computadoras arrancan en un sistema operativo. Cambiar entre sistemas operativos o instancias generalmente requiere una máquina separada. Hay soluciones de software que permiten que varios sistemas operativos se ejecuten simultáneamente en una sola máquina física:
+ **Emulación:** consiste en traducir las instrucciones que tiene un software montado en un hardware en otro software que no las tiene, por ejemplo, los emuladores de Nintendo para PC (DeSmuME).
+ **Virtualización:** un software llamado hipervisor se encarga de gestionar y asignar los recursos de hardware a las máquinas virtuales. Cada máquina virtual actúa como un entorno independiente, permitiendo ejecutar diferentes sistemas operativos simultáneamente.
+ **Paravirtualización:** consiste en modificar el sistema operativo invitado para que sea consciente de que se está ejecutando en un entorno virtualizado. A diferencia de la virtualización completa, donde el sistema operativo invitado no es consciente de la virtualización, en la paravirtualización, el sistema operativo invitado se modifica para cooperar mejor con el hipervisor o la capa de virtualización.

Además mediante el acceso remoto, con protocolos como SSH podemos controlar un sistema informático desde otro lugar de la red.

### Beneficios de la virtualización
+ Convierte el hardware en software.
+ Facilita la administración de sistemas.
+ Múltiples servidores separados pueden consolidarse como máquinas virtuales en un solo equipo físico.

### Problemas de la virtualición
+ Un fallo puede afectar a múltiples servicios (para ello se creó la High Accesibility).
+ Falta inicial de soporte por parte de los proveedores de software.
+ Servidores físicos más complejos.
+ Gestión crítica del rendimiento.
+ Gestión del almacenamiento compleja.

### Tipos de hipervisores
Una máquina virtual es una carpeta con una serie de ficheros que lee el hipervisor y los hace funcionar como un hardware. Clonar una máquina consiste simplemente en copiar y pegar esa carpeta. Existen 2 tipos de hipervisor:
+ Hipervisor instalado en el hardware.
+ Máquinas virtuales sobre un hipervisor sobre un sistema operativo sobre un hardware.
![[hipervisores.png]]

