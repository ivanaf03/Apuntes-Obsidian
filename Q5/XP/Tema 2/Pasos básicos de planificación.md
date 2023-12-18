[[Tema 2-Gestión y planificación de proyectos]]

### Pasos
1. Definir actividades e hitos.
2. Determinar las restricciones.
3. Asignar a cada actividad su duración en función del trabajo a realizar en cada una de ellas y sus recursos.
4. Obtener el camino crítico.
5. Afinar la planificación intentando mejorar el uso de recursos.
6. Establecer la línea base del proyecto, es decir, la planificación final.

### Definición de actividades
Para definir correctamente una actividad algunos parámetros importantes son:
+ Id de la actividad
+ Tipo de actividad
+ Descripción
+ Duración
+ Calendario
+ Fechas early y late
+ Porcentaje de completitud
+ Fecha real de comienzo

### Definición de restricciones
##### Start to Start (CC o SS)
La actividad B no puede comenzar mientras A no haya comenzado.

##### Start to Finish (SF o CF)
La actividad B no puede terminar hasta que A haya comenzado.

##### Finish to Start (FS o FC)
La actividad B no puede comenzar hasta que A no haya terminado.

##### Finish to Finish (FF)
La actividad B no puede terminar hasta que A haya terminado.

### Hamacas
Es un tipo de actividad que mide el tiempo transcurrido entre dos puntos de la red. Las restricciones se dan con las tareas elementales, no con las hamacas.

Simula una CC y una FF con el inicio y fin de la red de actividades. Sirve para ver un coste, por ejemplo, que no sabemos fijo de un recurso.

### Obtención del camino crítico
Los datos necesarios de partida son:
+ Las duraciones de las actividades
+ Las restricciones

Se analizan los tiempos:
+ Se calculan las fechas early
+ Se calculan las fechas late
+ Se calcula la holgura como de diferencia entre fechas late y fechas early. Las actividades sin holgura pertenecen al camino crítico

Una holgura negativa indica retraso antes de empezar el proyecto.

### Nivelación de recursos
Se deben asignar los recursos tras definir las actividades y saber que recursos tenemos. Tras ello hay que analizar las sobrecargas, por ejemplo, si un trabajo solo necesita 2 pintores, no se le asignan 3. 

Las posibles soluciones para las sobrecargas son:
+ Alargar las actividades
+ Cambiar los recursos de lugar
+ Introducir recursos que comparten el esfuerzo
+ Segmentar las actividades
+ Localizar los valles, es decir, las zonas donde un recurso no se está utilizando, y aprovecharlos

##### Eliminación de las sobrecargas
+ **A tiempo:** Se mantiene la fecha de fin y se modifican las actividades que no pertenecen al camino crítico. 
+ **A recurso:** Se puede variar la fecha fin del proyecto.

### Establecimiento de la línea base
La línea base es diferente en gestión de proyectos y en gestión de configuración software. En gestión de proyectos es el resultado final de la planificación. Sirve para ver, si el proyecto cambia, donde ha cambiado y qué hacer. Se usa en el seguimiento del proyecto una vez empezado. 