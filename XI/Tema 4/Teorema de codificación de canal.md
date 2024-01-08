[[Tema 4-Fundamentos de la codificación de canal]]

## Teorema
Dado un canal de comunicación, siempre existe una tasa máxima (bits por uso del canal en media) denominada capacidad C, a la cual la información puede ser transmitida fiablemente, i.e. con probabilidad de error tendiente a cero cuando el tamaño de palabra código tiende a infinito. Cualquier código escogido de forma de aleatoria permite alcanzar la capacidad del canal.

Si transmitimos a una tasa R = k/n (bits/(uso del canal) en media):
+ Si R<C, entonces los mensajes de la fuente pueden ser reconstruidos fiablemente.
+ Si R>C, entonces los mensajes de la fuente NO pueden ser reconstruidos fiablemente.

Imponer una estructura al código hace que no se alcance la capacidad de canal.

## Códigos turbo y LDPC
Ambos se basan en tener una estructura pseudoaleatoria y un tamaño de bloque muy grande. Los códigos LDPC son simplemente códigos con matriz H de control de paridad dispersa (pocos 1s y muchos 0s).

Los estándares LTE y 802.11 contemplan el uso de códigos convolucionales en los modos de transmisión más básicos. A diferencia de los códigos bloque, las palabras de un código convolucional se generan no sólo a partir de los bits de información actuales sino también con la información anterior en el tiempo. Es decir, un codificador convolucional es un sistema con memoria. Los códigos convolucionales no alcanzan la capacidad del canal.
 
