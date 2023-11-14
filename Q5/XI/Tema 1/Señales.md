 [[Tema 1-Fundamentos de la transmisión de señales]]

### Definición de señal
Una señal es una función o una magnitud física que varía en el tiempo, espacio o cualquier variable independiente y que contiene información acerca de cualquier fenómeno físico. 

Se puede representar matemáticamente como una función real de una variable independiente continua que toma valores en la recta real.
$f: \mathbb{R} \to \mathbb{R}$
$\ t \mapsto x(t)$

### Pulsos rectangulares
##### Pulso de duración T

$p1(t) =\begin{cases}1 & \text{si } 0 < t < T \\0 & \text{en el resto}\end{cases}$

![[pulso de duración T.png]]

##### Pulso de duración T centrado

$p2(t) =\begin{cases}1 & \text{si } -T/2 < t < T/2 \\0 & \text{en el resto}\end{cases}$

También se puede expresar como versión desplazada de p1(t):
$p2(t)=p1(t+T/2)$

![[pulso de duración T centrado.png]]

##### Señal escalón unidad
Es un pulso de duración infinita.
$u(t) =\begin{cases}1 & \text{si } t>0 \\0 & \text{en el resto}\end{cases}$

![[señal de duración infinita.png]]

Cualquier pulso rectangular se puede expresar en función de u(t):
$p(t)=u(t)-u(t-T)$

##### Tren de pulsos
Es la suma de versiones desplazadas de un pulso base.

![[tren de pulsos.png]]

$x(t)=p(t-0)-p(t-T)-p(t-2T)+p(t-3T)$

### Delta de Dirac o impulso unidad
Este modelo matemático, $\delta(t)$ se da cuando la amplitud de un pulso rectangular tiende a 0. Se representa como un vector vertical en t=0 de amplitud 1.

![[delta de Dirac.png]]

Propiedades:
+ $\delta(t)=0\ si\ t\ !=0$
+ $\delta(0)\ ->\ \infty$
+ $\int_{-\infty}^{+\infty} \delta(t) \, dt = 1$
+ Se puede multiplicar por una constante o desplazarse en el tiempo

### Señal senoidal
Son aquellas que se representan con la función coseno:
$x(t)=A*cos(2*\pi*f*t+\Phi)$


![[señal senoidal.png]]

##### Parámetros
La amplitud siempre es positiva. Es el parámetro que hace que el valor oscile entre
-A y A.

El periodo, $T0$, es la duración de un ciclo (separación entre dos mínimos). Es la inversa de la frecuencia.
$T0=1/f$

La frecuencia angular, $\omega$ se calcula como:
$\omega=2*\pi*f$

Por tanto:
$x(t)=A*cos(\omega*t+\Phi)$

La fase, $\Phi$, se mide en radianes y se puede interpretar como un desplazamiento en un tiempo t0. Si t0 es positivo da lugar a una fase negativa, si es negativo da lugar a una fase positiva. Sumar $\pi$ radianes a la fase de una señal senoidal equivale a cambiar de signo su amplitud. Se calcula como:
$\Phi=-\omega*t0$


### Señal sinc
$sinc(t)=\frac{sin(\pi)*t}{\pi*t}$

![[señal sinc.png]]

El pulso sinc vale 0 cuando t es un valor entero distinto de 0. En t=0 vale 1.