[[Tema 10-Virtualización de servidores]]

## ¿Qué es la live migration?
Es la migración sin problemas de máquinas virtuales en ejecución. No están nunca inactivas y no se pierden datos en la red. Es una transferencia del estado de la máquina entre dos hipervisores.

Permite mover las máquinas entre nodos. Se mueven por el estado de memoria virtual de la máquina. Lo que se hace a bajo nivel es copiar las páginas de memoria de un nodo a otro. Esto mismo se puede hacer de una cabina a otra. 

### Requisitos
+ Los hosts de origen y destino deben ser capaces de ejecutar la máquina virtual. 
+ Acceso a todo el almacenamiento utilizado por la máquina virtual. CPU compatibles.
+ Configuraciones de red comunes. 
+ Redes de alta capacidad. 
+ Plataforma de virtualización compatible.
+ Múltiples hosts en un clúster con CPUs compatibles.
+ Configuraciones de red comunes. 
+ Red de alta capacidad para los datos de migración.

### Problemas
+ Se requiere una red rápida y confiable para la sincronización. 
+ La compatibilidad de la CPU es muy estricta.
+ La migración en vivo que también traslada almacenamiento puede llevar mucho tiempo. 
+ Habrá límites en el número de migraciones concurrentes.

## Dynamic Load Balancing
Es un algoritmo de movimiento de máquinas que busca que los nodos no se saturen. Garantiza que los recursos se utilicen de manera efectiva y minimiza el impacto en las máquinas virtuales restantes en un clúster.

## Dynamic Power Management
No se usa casi nunca. Busca eficiencia energética. Consiste en mover las máquinas cuando no se están usando apenas, por ejemplo, por la noche, a un par de hipervisores y apagar los otros.