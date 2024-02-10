[[Tema 2-La máquina y el mundo]]

## Efecto en el entorno
Cuando hacemos software en lo que estamos interesados es en construir una máquina. Es decir, elaboramos un software que permite a un ordenador realizar funciones específicas. Tiene un efecto en el entorno.

El entorno es el mundo real que influye en nuestro problema. La máquina es lo que implementamos nosotros para solucionar algo en ese entorno.

Los requisitos son lo qué tiene que hacer la máquina, da igual cómo. Ese cómo es la forma en la que tenemos que implementar.

## Modelo WRSPM
El modelo WRSPM es un modelo formal donde tenemos un sistema y un entorno, dónde ocurren unos eventos llamados `eventos compartidos`. La zona que comparten el entorno y el sistema se denomina interfaz. La especificación de requisitos se hace a partir de estos eventos compartidos.

Lass siglas vienen de:
+ World Requirements (entorno)
+ Specification (interfaz)
+ Program Machine (sistema)

La especificación de requisitos es el puente que une el entorno con el sistema. Los requisitos son descritos en función del entorno. Buscamos que la especificación en función del conocimiento del dominio satisfaga los requisitos a la hora de implementar el sistema.

### Eventos compartidos
Eventos del entorno: $e_h$
Eventos del sistema: $s_h$
Eventos compartidos: $e_v, s_v$

La especificación de requisitos solo debe recoger solo los eventos que comparten el sistema y el entorno.