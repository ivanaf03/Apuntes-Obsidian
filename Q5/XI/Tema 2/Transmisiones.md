[[Tema 2-Análisis en frecuencia]]

## Mapeado Gray
Es una técnica de codificación en la cual dos números consecutivos solo difieren en un solo bit:
- Binario normal: 000, 001, 010, 011, 100, 101, 110, 111
- Código Gray: 000, 001, 011, 010, 110, 111, 101, 100

## Transmisiones
### Transmisión banda base
Es la transmisión de señales que ocupan un rango de frecuencias centrado alrededor de la frecuencia cero (o frecuencia base). En este tipo de transmisión, la señal original (mensaje) se envía directamente sin modular sobre una portadora. Esto significa que la señal se transmite en su forma original, sin cambiar su frecuencia central.

Según el teorema de Nyquist, para calcular el ancho de banda:
$$B=v_s/2$$

### Transmisión paso banda
Implica modular una señal de información sobre una portadora de frecuencia específica antes de transmitirla. En este caso, la señal original se desplaza en frecuencia hacia arriba o hacia abajo, creando una señal modulada en banda base. Esta señal modulada se llama señal paso banda y ocupa un rango de frecuencias centrado alrededor de la frecuencia de la portadora.

En sistemas de comunicación de paso banda, la información se transmite mediante la modulación de una portadora en una frecuencia específica. La velocidad de símbolo se asocia directamente con la frecuencia de la portadora y, por lo tanto, el ancho de banda de la señal modulada es igual a la velocidad de símbolo.

$$B=v_s$$
