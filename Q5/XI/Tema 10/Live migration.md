[[Tema 10-Virtualización de servidores]]

Permite mover las máquinas entre nodos. Se mueven por el estado de memoria virtual de la máquina. Lo que se hace a bajo nivel es copiar las páginas de memoria de un nodo a otro.

Esto mismo se puede hacer de una cabina a otra. 

## Dynamic Load Balancing
Es un algoritmo de movimiento de máquinas que busca que los nodos no se saturen. 

## Dynamic Power Management
No se usa casi nunca. Busca eficiencia energética. Consiste en mover las máquinas cuando no se están usando apenas, por ejemplo, por la noche, a un par de hipervisores y apagar los otros.