[[Borrador de diseño de un Centro de Proceso de Datos]]

(BORRADOR)

## 1.Componentes del grupo
+ Grupo 3.XI.3.2
+ Día de prácticas: Viernes 8:30-10:30
+ Autores: 
	+ Iván Álvarez Fernández:  
        ivan.alvarez.fernandez@udc.es
	+ Ivanna Pombo Casais:     
		ivanna.pombo@udc.es
	+ Fernando Álvarez Rodríguez de Legísima:
		fernando.alvarezr@udc.es

## 2.Introducción
  
La tarea consiste en diseñar un Centro de Proceso de Datos (CPD) utilizando una solución modular y escalable. Se abordan aspectos clave como la distribución de elementos en racks, la topología de red, el sistema eléctrico con un enfoque en eficiencia energética, la refrigeración mediante InRows y cerramientos de pasillo caliente, y la implementación de sistemas de seguridad como firewalls. Se enfatiza en la importancia de la integración global de la infraestructura para garantizar un funcionamiento eficiente y efectivo del CPD.

## 3.Distribución de carga de TI en los racks
+ Chasis HPE Synergy 12000 Frame: 10 Rack Units
+ Switch Cisco MDS 9132T: 1 Rack Unit
+ Switch Cisco Nexus 3048: 1 Rack Unit
+ Switch Cisco Nexus 9316D-GX: 1 Rack Unit
+ Controladora HPE 3 PAR 9450 Storage Node (Q7F41A): 8 Rack Units
+ Disco SAS Drive Enclosure (Q0E95A): 2 Rack Units
+ Router Cisco C8300-1N1S-6T: 1 Rack Unit
+ Firewall Cisco ASA5516-X: 1 Rack Unit
+ Servidor rack HPE Proliant DL20: 1 Rack Unit
+ Rack: 42 Rack Unit

Se cerraran los pasillos con puertas y se aislará el techo con paneles para un mayor aislamiento térmico.

Los rack de los diagramas (ver abajo) tienen una ocupación del 100% de las RU. Deberíamos añadir para futuras expansiones otro rack por fila vacío. De esta forma tendríamos:
+ 18 racks (contando los 2 vacíos), en total 774 RUs.

$Porcentaje\ de\ ocupación=672/774=0,8682=86,83\%$
$Porcentaje\ libre=102/774=0,1317=13,17\%$

Hemos decido situar centrados los racks con los sistemas de almacenamiento y los router y firewall para acortar la distancia y cantidad de cableado con el resto de elementos del CPD.

### Diseño del CPD (vista aérea)
![[cpd1.png]]
### Diseño de racks
![[cpd2.png]]

## 4.Distribución de los equipos de red en los racks y su interconexión
![[cpd3.png]]