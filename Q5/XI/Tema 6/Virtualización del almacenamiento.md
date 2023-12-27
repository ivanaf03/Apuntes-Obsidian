[[Tema 6-Redes de almacenamiento]]

## SDS
El SDS o Almacenamiento Definido por Software permite una abstracción de los recursos de almacenamiento local, facilitando el uso de funcionalidades de HA, balanceo y seguridad. Permite granularizar el almacenamiento.

Sus ventajas son:
+ Permite utilizar soluciones de almacenamiento de diferentes fabricantes sin que las aplicaciones tengan que preocuparse por los detalles específicos del hardware subyacente.
+ Se incluyen políticas de protección, como diferentes tipos de RAID.
+ Se pueden integrar diferentes discos o cloud sin depender de un proveedor específico.

### VM-Centric
A diferencia de la protección a nivel de LUN o volumen en un almacenamiento de área de red (SAN) tradicional, la provisión de protección a nivel de máquina virtual se centra en satisfacer los requisitos específicos de cada máquina virtual individualmente. Se basa en tiers:
+ **Tier 1:** Alto rendimiento. Utiliza RAID 10 y discos SAS.
+ **Tier 2:** Rendimiento medio. Utiliza RAID 5 y discos SAS.
+ **Tier 3:** Bajo rendimiento. Utiliza RAID 5 y discos SATA. 

## Almacenamiento de datos
### Agrupación de discos
Consiste en combinar varios discos físicos para formar un conjunto que pueda proporcionar mayores capacidades y/o un mejor rendimiento. 

Utilizan un dispositivo flash, como un SSD, que se utiliza como caché para mejorar el rendimiento del sistema al almacenar temporalmente datos frecuentemente accedidos. Cada dispositivo de almacenamiento en caché debe estar dedicado a un conjunto específico de discos.

Existen 2 tipos de agrupaciones:
- **All-Flash:** tanto el caché como la capacidad de almacenamiento utilizan tecnología flash. Este enfoque maximiza el rendimiento al utilizar exclusivamente dispositivos de estado sólido.
- **Híbridos:** el caché utiliza tecnología flash, mientras que la capacidad de almacenamiento utiliza discos magnéticos (SAS o SATA). Los dispositivos híbridos buscan equilibrar el rendimiento mejorado del caché flash con la capacidad más económica de los discos magnéticos.

### Almacenamiento basado en objetos
Los datos se almacenan y administran en contenedores flexibles denominados objetos. Cada objeto es dividido en componentes y distribuido por varios discos virtuales, junto con los metadatos que permiten localizar las réplicas de los segmentos del objeto a través del almacén de datos (datastore). 

Cada objeto se aprovisiona y administra de forma individual, lo que incluye una segmentación y configuración RAID específica para cada objeto. Estas directivas son dinámicas y pueden actualizarse o cambiarse en cualquier momento.

Cuando se crea un objeto para un disco virtual, a la hora de distribuir el objeto por un clúster:
+ Se comprueba la configuración de directivas de almacenamiento que aplican al objeto.
+ Se revisa el uso de recursos.
+ Se mantiene una monitorización constante.
+ Se busca alta disponibilidad de las copias y testigos en host separados o en dominios de fallo diferentes (distintos racks, filas, CPDs).

Cada clúster funciona como un único almacén de datos y pueden proporcionar diferentes servicios. El sistema de almacenamiento segmentará, replicará y colocará cada objeto de modo óptimo en función de las políticas del servicio.

### Dominios de fallos
A la hora de decidir donde ubicar las distintas réplicas de un objeto se tienen en cuenta los dominios de fallo o dominios de errores (rack, fila, CPD).

Los distintos segmentos de un objeto son distribuidos y replicados por el almacén de datos, haciendo uso de un testigo que contiene los metadatos que permiten decidir si un objeto está en estado correcto, es decir, cuenta con el número mínimo de segmentos replicados para poder reconstruirse.

Se utiliza un sistema de votación asimétrico, es decir, no todos los votos tendrán el mismo peso, para decidir el número de votos mínimo para determinar la disponibilidad de un objeto. Para que un objeto se considere correcto, la accesibilidad de los votos que componen el objeto debe ser superior al 50%.

Un Witness es un componente que almacena metadatos y se utiliza para desempatar y resolver conflictos en situaciones donde dos dominios de fallo quedan aislados. Proporciona un mecanismo para decidir cuál es la copia válida de los datos y contribuye a la consistencia y la integridad en entornos distribuidos.

### Disaster Recovery
El RPO (Recovery Point Objective) es el volumen de datos en riesgo de pérdida que una organización está dispuesta a asumir. Se refiere al punto en el tiempo hasta el cual una organización puede aceptar perder datos en caso de un desastre. Se mide en base al número de copias de respaldo.

El RTO (Recovery Time Objective) es el tiempo que transcurre entre que ocurre el desastre y se logra recuperar el sistema. Es el tiempo máximo que una organización puede tolerar estar sin acceso a sus sistemas después de un desastre. 

En base a esos factores se suelen establecer 3 modelos de sistemas:
+ **Esenciales:** RTO<15 min
+ **Importantes:** RTO<2 h, RPO 4 h
+ **Otros:** RTO<4 h, RPO 24 h