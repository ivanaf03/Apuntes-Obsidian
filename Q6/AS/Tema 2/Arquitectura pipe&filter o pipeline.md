[[Tema 2-Arquitecturas de división de responsabilidades]]
$\space$
## 1.Qué es la arquitectura pipe&filter
El pipe&filter es una arquitectura muy similar a la arquitectura en capas. Se basa en transformar entradas en salidas. 

Organiza el sistema en una serie de pasos llamados filtros. Las peticiones pasan a través de los filtros a través del pipe hasta la salida. A diferencia de la arquitectura en capas, no hace dos veces el ciclo, es lineal.
$\space$
### 1.1.Ventajas e inconvenientes
La arquitectura pipe&filter:
+ [p] Permite añadir muy fácilmente filtros, eliminarlos o modificar alguno de ellos.
+ [c] La salida es diferente a la entrada, por lo que no se puede usar para sistemas interactivos.
$\space$
## 2.Diagramas
Veremos el diagrama de contexto y de contenedores.
$\space$
### 2.1.Diagrama de contexto

![[contexto pipe.png]]
$\space$
### 2.2.Diagrama de contenedores

![[contenedores pipe.png]]
$\space$
## 3.Características
Esta arquitectura se suele usar en sistemas dedicados al procesamiento de información.

La lógica de negocio se distribuye a lo largo de todo el sistema. Permite añadir con facilidad filtros, eliminarlos, reusarlos, etc. Además, mejora mucho en rendimiento frente a la arquitectura en capas, ya que puede procesar varias peticiones a la vez.

El problema es que la entrada y la salida son diferentes puntos del sistema y muchas veces no se puede usar esta arquitectura. Para evitar problemas de rendimiento debido a formateos, la información debe compartirse en un formato válido para los distintos filtros.
