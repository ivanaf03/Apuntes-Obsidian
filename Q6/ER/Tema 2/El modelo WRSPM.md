[[Tema 2-La máquina y el mundo]]

# La máquina y el entorno
La función del software es permitir a una máquina realizar funciones específicas. La máquina tiene un efecto en el entorno.

El entorno es la parte del mundo real que influye en nuestro problema. Las máquinas buscan solucionar los problemas que ocurren en ese entorno.

Los requisitos son el qué tiene que trabajar la máquina, no importa el cómo. La implementación es el cómo.

# Modelo WRSPM
El modelo WRSPM es un modelo formal compuesto por un sistema y un entorno, relacionados por unos eventos llamados `eventos compartidos`. La zona que comparten el entorno y el sistema se denomina interfaz. La especificación de requisitos se hace a partir de estos eventos compartidos.
![[WRSPM.png]]
+ [i] **Siglas:**
+ World-Requirements (entorno)
+ Specification (interfaz)
+ Program-Machine (sistema)

La especificación de requisitos es el puente que une el entorno con el sistema. Los requisitos son descritos en función del entorno. Buscamos que la especificación en función del conocimiento del dominio satisfaga los requisitos a la hora de implementar el sistema.

## Eventos
+ [<] **Eventos:**
*Eventos del entorno:* $e_h$
*Eventos del sistema:* $s_h$
*Eventos compartidos:* $e_v, s_v$

La especificación de requisitos solo debe recoger solo los eventos que comparten el sistema y el entorno.