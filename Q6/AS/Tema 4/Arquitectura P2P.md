[[Tema 4-Arquitecturas centradas en la comunicación]]
$\space$
## 1.Qué es la arquitectura P2P?
Se basa en estructurar un sistema en componentes equivalentes que sean todos capaces de realizar una tarea. Son sistemas descentralizados en los que cualquier componente puede atender una petición. Puede ser totalmente descentralizada o puede tener un super-peer central.
$\space$
### 1.1.Ventajas e inconvenientes
La arquitectura P2P:
+ [p] Permite un reparto uniforme y descentralizado de la carga, por lo que es muy escalable y brinda una gran disponibilidad.
+ [c] No es muy segura.
+ [c] Los componentes nos están sincronizados y coordinados. 
$\space$
## 2.Diagramas
Veremos el diagrama de contexto y de contenedores.
$\space$
### 2.1.Diagrama de contexto

![[p2p contexto.png]]
$\space$
### 2.2.Diagrama de contenedores

![[contenedores p2p.png]]

Nota: faltan las flechas entre peers.
$\space$
## 3.Características
Esta arquitectura se usa en sistema en que los pares transmiten información entre ellos o en sistemas donde se usa un servidor cuya única función es avisar a cada nodo de cuales son sus vecinos. 

Es la arquitectura que aprovecha de forma más óptima los recursos disponibles del sistema. El problema es que pare introducir medidas de seguridad o comunicar pares muchas veces es necesario el super-peer.