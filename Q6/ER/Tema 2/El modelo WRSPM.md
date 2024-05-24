[[Tema 2-La máquina y el mundo]]
$\space$
## 1.La máquina y el entorno
La función del software es permitir a una máquina realizar funciones específicas. Las máquinas producen un efecto en el entorno. El entorno es la parte del mundo real que afecta al problema planteado. La intención es que las máquinas solucionen los problemas que ocurren en ese entorno.

Para saber qué tiene que hacer la máquina se utilizan los requisitos. De los requisitos se saca una implementación, que es el resultado del "cómo" se afronta el problema.
$\space$
## 2.Modelo WRSPM
El modelo WRSPM es un modelo formal compuesto por un sistema y un entorno que se relacionan entre sí a través de eventos compartidos. La zona que une el sistema y el entorno se conoce como interfaz. Esta contiene los eventos compartidos, que permiten elaborar la especificación de requisitos.

![[WRSPM.png]]
$\space$
### 2.1.Significado de WRSPM
Las letras significan:
+ **W(orld):** mundo, contexto donde se desarrolla el problema.
+ **R(equirements):** requisitos.
+ **S(pecification):** especificación de requisitos.
+ **P(rogram):** software a desarrollar.
+ **M(achine):** máquina donde se instala el software.
$\space$
## 3.Eventos
Los eventos pueden ser ocultos ($e_h$, $s_h$) o visibles ($e_v$, $s_v$). 

Los visibles son aquellos que pueden ser detectados o influenciados tanto por el sistema como por el entorno. Pueden ser parte de las interacciones del sistema con los usuarios finales, con otros sistemas o con el entorno físico en el que opera. Estos son los eventos compartidos.

Por otro lado, los eventos ocultos son aquellos que ocurren dentro del sistema pero que no son directamente observables desde fuera del sistema. Por ejemplo, acciones internas del sistema, cambios de estado o procesos que no son visibles para los usuarios finales o para otros sistemas externos. Estos son los eventos tanto del sistema como del entorno que no son compartidos.