[[Tema 10-Virtualización de servidores]]

## Almacenamiento
Las piezas de almacenamiento suelen ser siempre el problema de rendimiento. 

El disco de cada máquina genera una carpeta vmdk (en vmware). Los sistemas de virtualización de VMWare no se adaptaban a los sistemas de ficheros estándar (ext4, ntfs...). Por eso diseñaron VMFS. Permite a varios nodos escribir de forma paralela en disco.

### Discos duros
Es necesario comprender los conceptos básicos de las tecnologías de almacenamiento y cómo funcionan para apreciar completamente la importancia del almacenamiento en la infraestructura virtualizada
+ Discos duros
	- Unidades electromecánicas
	- Alta capacidad
	- Relativamente lentos
	- Rentables
-  Dispositivos de estado sólido (SSD)
	- 0% componentes mecánicos
	- Menor capacidad
	- Rendimiento alto
	- Relativamente costosos 
SAS es el tipo de interfaz dominante para servidores, ya que proporciona más características de gestión de almacenamiento y permite la conexión de más dispositivos a velocidades más altas.

### RAID
Configurar cantidades muy grandes de almacenamiento para un servidor es complejo. Puede ser necesario un gran número de unidades. Contar con muchas unidades aumenta el riesgo de fallas de unidades. RAID proporciona una forma de agregar y gestionar múltiples unidades. Las matrices SAN y NAS ofrecen soluciones de almacenamiento de alta capacidad basadas en red y proporcionan un rendimiento increíblemente alto.

Los RAID más usados son:
+ **RAID 0:** Rápido pero sin protección. 
+ **RAID 1:** Rápido pero no eficiente. 
+ **RAID 5:** Relativamente lento pero con buena protección y eficiencia. 
+ **RAID 6:** El más lento pero con la mejor protección y eficiencia.

## Sistema de ficheros
Un sistema de archivos normalmente se asigna a un solo disco físico o bloque de almacenamiento de una matriz o SAN. Los sistemas de archivos pueden abarcar varios discos mediante puntos de montaje o extensiones. Cada sistema de archivos tendrá límites en el tamaño de los archivos, la capacidad máxima, etc. Los archivos pueden contener otros archivos o incluso imágenes de disco.

Las máquinas virtuales deben tener discos virtuales configurados para ellas. Los discos virtuales se presentan a la máquina virtual de la misma manera en que los discos físicos se presentan a una máquina física. Los archivos de disco virtual contienen los datos en bruto para esos discos.