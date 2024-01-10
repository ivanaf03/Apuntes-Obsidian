[[Tema 10-Virtualización de servidores]]
## Asiganación de recursos a VM
Se puede sobredimensionar la asignación de recursos. Si tenemos 32 CPU por ejemplo, podríamos asignar:
+ MV1: 8 CPU
+ MV2: 16 CPU
+ MV3: 16 CPU

En total sumarían 40 CPU. Esto se puede hacer suponiendo que las máquinas no usarán más de las 32 físicas de las que disponemos a la vez. Lo que no se podría hacer ni tendría sentido sería dar más de 32 CPU a una máquina virtual.

Se puede hacer lo mismo con la RAM, pero no tan a la ligera. Se estima que se podría dar una suma virtual total de 1,33/1,5 veces la capacidad física en RAM y en CPU 6/10 veces.

### Tecnologías de Virtualización de Memoria de VMware
Se ejecutan de más memoria a menos memoria disponible:
- Compartición Transparente de Páginas
- Recuperación de Memoria mediante Inflado de Invitados
- Compresión de Memoria
- Intercambio de Memoria Virtual

## Conexiones
Los switches conectan directamente máquinas en redes locales de corto alcance. Ethernet es la tecnología de red local dominante en la actualidad. Las direcciones IP y los routers permiten la conexión de redes locales conmutadas.

Un hipervisor simula internamente el proceso de conmutación para conectar máquinas virtuales entre sí. Se pueden configurar múltiples conmutadores virtuales para controlar qué máquinas virtuales pueden conectarse entre sí. Dentro de un solo hipervisor, la velocidad de las conexiones de red entre máquinas virtuales es controlada por el hipervisor. El enrutamiento se puede hacer, pero se implementaría utilizando software que se ejecuta dentro de las máquinas virtuales.

Estos conmutadores se pueden conectar a redes físicas. Los enlaces ascendentes (uplinks) a conmutadores físicos se configuran utilizando adaptadores de red físicos en el hipervisor. 