[[Tema 3-IEEE 802.11]]

## Canales de radio
+ **Canales de 2.4 GHz:** 
	+ Mayor distancia de propagación.
	+ Solapamiento de canales.
+ **Canales de 5 GHz:**
	+ Menor distancia de propagación.
	+ No solapamiento de canales .
	+ Canales DFS (Dynamic Frequency Selection): canales en los que es obligatorio poder dejar de usarlos en caso de que pasen a estar ocupados por aplicaciones tipo radar y comunicaciones satélite.

Cada modulación tiene una eficiencia espectral, $\eta$:
+ BPSK: ƞ = 1 bit/s/Hz 
+ QPSK: ƞ = 2 bit/s/Hz 
+ M-QAM: ƞ = log2 M bit/s/Hz

Se añaden bits redundantes (codificación) para compensar el ruido del canal. Por cada k bits fuente se transmiten n bits codificados. Tasa de codificación:
$$R=k/n$$

### Ejercicio modulación
![[modulación.png]]

### Ejercicio modulación 2
![[modulación 2.png]]

## IEEE 802.11: OFDM
En lugar de transmitir (a) una señal de banda ancha (período de símbolo pequeño, alta velocidad), transmitimos (b) una superposición de portadoras, que son señales de banda estrecha (período de símbolo grande, velocidad baja).

Cada portadora se ve afectada por el canal de modo independiente.
![[ofdm.png]]

La velocidad de bit se calcula como:
$$v_b = \frac{C}{T_{\text{DFT}} + T_{\text{GI}}}$$
+ C es la cantidad de subportadoras.
+ Tdft es la duración de símbolo.
+ Tgi es el intervalo de guarda.


La eficiencia se calcula como:
$$e=x/x_{max}$$

![[tabla tasas.png]]![[ejercicios eficiencia.png]]