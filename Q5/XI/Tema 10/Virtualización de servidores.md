[[Tema 10-Virtualización de servidores]]

Se puede sobredimensionar la asignación de recursos. Si tenemos 32 CPU por ejemplo, podríamos asignar:
+ MV1: 8 CPU
+ MV2: 16 CPU
+ MV3: 16 CPU

En total sumarían 40 CPU. Esto se puede hacer suponiendo que las máquinas no usarán más de las 32 físicas de las que disponemos a la vez. Lo que no se podría hacer ni tendría sentido sería dar más de 32 CPU a una máquina virtual.

Se puede hacer lo mismo con la RAM, pero no tan a la ligera. Se estima que se podría dar una suma virtual total de 1,33/1,5 veces la capacidad física en RAM y en CPU 6/10 veces.

## VMware Memory Virtualization Technologies
Se ejecutan de más memoria a menos memoria disponible.

