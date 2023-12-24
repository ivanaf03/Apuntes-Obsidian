 [[Tema 1-Fundamentos de la transmisión de señales]]

## Definición de señal
Una señal es una función o una magnitud física que varía en el tiempo, espacio o cualquier variable independiente y que contiene información acerca de cualquier fenómeno físico. 

Se puede representar matemáticamente como una función real de una variable independiente continua que toma valores en la recta real.
$$f: \mathbb{R} \to \mathbb{R},\ t \to x(t)$$

## Pulsos rectangulares
  
Un pulso rectangular, también conocido como función escalón rectangular o pulso cuadrado, es una función matemática que toma el valor de 1 en un intervalo específico y 0 fuera de ese intervalo. La forma general de un pulso rectangular es:
$$u(t; a, b) = \begin{cases} 
    1 & \text{si } a \leq t \leq b \\
    0 & \text{en otro caso}
\end{cases}
$$

### Pulso de duración T
$$p1(t) =\begin{cases}1 & \text{si } 0 < t < T \\0 & \text{en otro caso}\end{cases}$$
![[pulso de duración T.png]]

### Pulso de duración T centrado
$$p2(t) =\begin{cases}1 & \text{si } -T/2 < t < T/2 \\0 & \text{en otro caso}\end{cases}$$

También se puede expresar como versión desplazada de p1(t):
$$p2(t)=p1(t+T/2)$$
![[pulso de duración T centrado.png]]

### Señal escalón unidad
Es un pulso de duración infinita.
$$u(t) =\begin{cases}1 & \text{si } t>0 \\0 & \text{en otro caso}\end{cases}$$
![[señal de duración infinita.png]]

Cualquier pulso rectangular se puede expresar en función de u(t):
$$p(t)=u(t)-u(t-T)$$

### Tren de pulsos
Es la suma de versiones desplazadas de un pulso base. Por ejemplo:
![[tren de pulsos.png]]

$$x(t)=p(t-0)-p(t-T)-p(t-2T)+p(t-3T)$$

## Delta de Dirac o impulso unidad
Este modelo matemático, $\delta(t)$ se da cuando la amplitud de un pulso rectangular tiende a 0. Se representa como un vector vertical en t=0 de amplitud 1.
![[delta de Dirac.png]]

Propiedades:
+ $\delta(t)=0\ si\ t\ \neq 0$
+ $\delta(0) \rightarrow \infty$
+ $\int_{-\infty}^{+\infty} \delta(t) \, dt = 1$
+ Puede multiplicarse por una constante o desplazarse en el tiempo.

## Señal senoidal
Son aquellas que se representan con la función coseno:
$$x(t)=A*cos(2*\pi*f*t+\Phi)$$

También se puede representar con la función seno:
$$x(t) = A \sin(2\pi f t + \phi)$$

La onda coseno comienza en su valor máximo. La onda seno comienza en su valor cero.
![[señal senoidal.png]]

### Parámetros
+ **Amplitud (A):** Siempre es positiva. Es el valor máximo que alcanza la señal con respecto a su línea de base.
+ **Periodo (T0):** Es la duración de un ciclo, es decir, la separación entre dos mínimos. Es la inversa de la frecuencia.
$$T0=1/f$$
Por otra parte, la frecuencia angular, $\omega$ se calcula como:
$$\omega=2*\pi*f$$
+ **Fase ($\Phi$):** posición relativa de la onda en el tiempo. Indica en qué punto específico de ese ciclo se encuentra la onda en un momento dado. Se calcula como:
$$\Phi=-\omega*t0$$

Por tanto, la fórmula de la señal senoidal se simplifica en:
$$x(t)=A*cos(\omega*t+\Phi)$$

El desfase es un cambio en la fase de una señal en comparación con otra señal de referencia o en comparación con su propio estado inicial. Puede ser:
+ **Desfase positivo:** Un desfase positivo implica un adelanto en la fase de la onda. La onda comienza su ciclo antes de lo que lo haría normalmente. Visualmente, se observa como un desplazamiento hacia la izquierda en la gráfica de la onda senoidal.
+ **Desfase negativo:** Un desfase negativo implica un retraso en la fase de la onda. La onda comienza su ciclo después de lo que lo haría normalmente. Visualmente, se observa como un desplazamiento hacia la derecha en la gráfica de la onda senoidal.
![[desfase.png]]

## Señal sinc
El pulso sinc vale 0 cuando t es un valor entero distinto de 0. En t=0 vale 1. Es utilizada para representar idealmente el espectro de frecuencia de una señal rectangular. Su transformada de Fourier es una función rectangular.
$$sinc(t)=\frac{sin(\pi)*t}{\pi*t}$$
![[señal sinc.png]]
