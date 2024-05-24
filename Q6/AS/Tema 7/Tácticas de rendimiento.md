[[Tema 7-Rendimiento]]
$\space$
## 1.Para que sirven las tácticas de rendimiento?
El rendimiento se evalúa en función de la respuesta del sistema ante eventos temporales. Por tanto, las tácticas tratan de controlar la latencia.

Puede hacerse con:
+ Espera activa
+ Espera inactiva
$\space$
### 1.1.Tácticas
Pueden ser:
+ **De demanda de recursos:**
	+ **Incremento de la eficiencia computacional:** se optimiza la eficiencia de los algoritmos, de la recursividad, bucles, etc.
	+ **Reducción de la sobrecarga computacional:** reducir la cantidad de intermediarios.
	+ **Gestión del ratio de eventos:** reducir la frecuencia con la que se tratan los eventos. Por ejemplo, descartándolos si no controlamos su llegada.
	+ **Control de la frecuencia de muestreo:** reducir la frecuencia de monitorización.
	+ **Limitación del tiempo de ejecución:** limitar el tiempo de espera de las respuestas.
	+ **Limitación del tamaño de los buffers:** limitar la cantidad de eventos pendientes de ser procesados.
+ **De gestión de recursos:**
	+ **Introducción de concurrencia:** paralelización de peticiones y balanceo de carga.
	+ **Replicación de datos o procesos:** datos y procesos duplicados para reducir el tiempo de espera, pero el sistema debe mantener la integridad de la información.
	+ **Incremento de los recursos disponibles:** es caro, pero mejorar el hardware mejora el rendimiento.
+ **De arbitraje de recursos:**
	+ **FIFO:** todas las peticiones se atienden en orden de llegada, en cola.
	+ **Prioridad fija:** cola de prioridad. Genera inanición en las peticiones con baja prioridad.
	+ **Prioridad dinámica:** cola de prioridad cambiante. Por ejemplo, mediante el algoritmo de Round Robin.
	+ **Arbitraje estático:** asignaciones antes de la ejecución del sistema.