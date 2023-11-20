[[Tema 6-Redes de almacenamiento]]

### Métodos de transferencia
Los datos pueden transferirse a través de la red de dos modos diferentes:
+ **Modo fichero:** permite transferir datos en forma de archivos a través de la red. Se utiliza con sistemas de almacenamiento compartido NAS (Network Attached Storage). 
+ **Modo bloque**: los datos se transfieren en bloques sin tener que convertirlos en archivos. Se utilizan en entornos de almacenamiento  conectado directamente DAS-SAN (Direct Attached Storage-Storage Area Network).

##### Acceso a modo fichero
+ Necesita más procesamiento, ya que los sistemas tienen que  trabajar con la estructura de archivos y directorios.
+ Proporciona mayor nivel de abstracción.
+ Suelen tener una latencia mayor.
+ Es más sencillo de implementar en los SO.

##### Acceso a modo bloque
+ Es más rápido y tiene menos latencia, ya que no hay una capa de gestión de archivos.
+ Es más difícil de configurar, ya que hay que trabajar a más bajo nivel.

### Sistemas tradicionales
Un sistema de almacenamiento tradicional consta de cabinas equipadas con controladoras, que se conectan a bandejas de discos que pueden contener diversos tipos de discos. Esta configuración permite adaptarse a las necesidades específicas de almacenamiento y rendimiento de una organización.

Las cabinas de almacenamiento son dispositivos de hardware que proporcionan almacenamiento masivo. Están equipadas con procesadores, controladoras y cachés especializadas para gestionar y servir bloques de datos almacenados en discos.

Están compuestas por:
+ **Controladora:** es la unidad central de procesamiento en la cabina de almacenamiento. Funciona con un sistema operativo específico y está equipada con procesadores especializados y memoria caché (NVRAM) para mejorar la velocidad de acceso a los datos. Se conecta al entorno mediante tecnologías como DAS o SAN utilizando protocolos como Fibre Channel o iSCSI.
+ **Bandejas de discos o enclosures:** son estructuras físicas que contienen discos duros. Pueden alojar diferentes tipos de discos. Permiten soluciones híbridas, que combinan el rendimiento rápido de los SSD con la capacidad de almacenamiento más grande de los discos tradicionales, y all-flash, que utilizan exclusivamente SSD o NVMe para lograr un rendimiento máximo.

##### Tipos de discos duros
+ **SAS:** discos de alta velocidad y rendimiento.
+ **SATA:** discos económicos con menor velocidad y rendimiento que los SAS.
+ **SSD:** discos de estado sólido que ofrecen un rendimiento significativamente más rápido en comparación con los discos duros tradicionales.
+ **NVMe:** discos con interfaz de almacenamiento que permite una comunicación más rápida entre el sistema y los dispositivos de almacenamiento, ofreciendo un rendimiento extremadamente alto.

##### Partes
+ **Agregado:** conjunto de discos físicos que están ubicados dentro de bandejas de discos gestionados como una unidad única por un controlador. Sirve para aislar cargas de trabajo.
+ **Volumen:** representación lógica del almacenamiento o un contenedor de datos.
+ **LUN (Logical Unit Number):** conjunto de bloques dentro de un volumen que tiene un identificador único, comúnmente conocido como WWPN (World Wide Port Name). Puede ser servido al host a través de protocolos como Fibre Channel o SCSI, y puede estar en formato "thin", asigna espacio a medida que se necesita, o "thick", que asigna todo el espacio al principio, independientemente de si se utiliza o no.