[[Tema 4-Fundamentos de la codificación de canal]]

## Probabilidad de error general
La probabilidad de error será, como mucho, igual a la probabilidad de que el canal introduzca más de t errores. “Como mucho”, ya que puede haber patrones de error con más de t errores que el código sea capaz de corregir.
![[pwe.png]]
## Probabilidad de error de bit
Cada palabra código no corregida por el código tendrá t + 1 errores (en los bits codificados). En media, tendremos (𝑘/𝑛)\*(𝑡 + 1) errores en los bits fuente en cada palabra código no corregida por el código. Si transmitimos N >> 1 palabras, tendremos 𝑁𝑝we palabras no corregidas por el código. Por tanto, la probabilidad de error de bit fuente es:
![[pbe.png]]

## Probabilidad de error en canal AWGN
![[awgn.png]]