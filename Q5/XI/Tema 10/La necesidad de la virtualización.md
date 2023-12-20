[[Tema 10-Virtualización de servidores]]

Un servidor debe tener CPU, memoria, disco duro y red. Al principio eran mainframes, ahora han pasado a redes de máquinas mucho más pequeñas conectadas entre sí.

Hace años una sola aplicación corría sobre un sistema operativo en un servidor. Se hacía así para evitar problemas de dependencias, de robo de recursos...

Hace unos años, se empezaron a aislar las aplicaciones en un solo servidor. Esto evolucionó separando el disco en cabinas. Esto era el estándar de los CPD hasta 2015/16.

Sin embargo, las cabinas son muy caras y difíciles de gestionar. De ahí surge la hiperconvergencia. Consiste en volver a meter el disco en los servidores, pero virtualizando el almacenamiento. Este software convierte todos los discos de los servidores en una simulación de una cabina. Además los datos están redundados en más de un nodo.

## Virtualización. emulación y paravirtualización
Emular consiste en traducir las instrucciones que tiene un software en un hardware en otro software que no las tiene, por ejemplo, los emuladores de Nintendo para PC (DeSmuME).

Un virtualizador asigna la cantidad de recursos necesarios a cada máquina a medida de lo que necesiten. 

## Beneficios de la virtualización
+ Son capaces de administrar mejor el hardware.
+ Facilita la administración de sistemas.

## Problemas
+ Un fallo puede afectar a múltiples servicios (para ello se crearon las High Accesibility).

## Tipos de servidores
+ Tipo 1: el hipervisor va instalado en el hardware.
+ Tipos 2: máquinas virtuales sobre un software sobre un sistema operativo sobre un hardware.

## Máquina virtual
Una máquina virtual es una carpeta con una serie de ficheros que lee el hipervisor y los hace funcionar como un hardware. 