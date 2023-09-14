[[Tema 1-Fundamentos de la transmisión de señales]]

### Definición de señal
Una señal es una función o una magnitud física que varía en el tiempo, espacio o cualquier variable independiente y que contiene información acerca de cualquier fenómeno físico. 

Se puede representar matemáticamente como una función real de una variable independiente continua que toma valores en la recta real.
$t->x(t)$

### Pulsos rectangulares
+ Señal de duración T
$p1(t) =\begin{cases}1 & \text{si } 0 < t < T \\0 & \text{en el resto}\end{cases}$
![[pulso de duración T.png]]

+ Señal de duración T centrada
$p2(t) =\begin{cases}1 & \text{si } -T/2 < t < T/2 \\0 & \text{en el resto}\end{cases}$
$p2(t)=p1(t+T/2)$
![[pulso de duración T centrado.png]]

### Señal escalón unidad
$u(t) =\begin{cases}1 & \text{si } t>0 \\0 & \text{en el resto}\end{cases}$
![[señal de duración infinita.png]]

$p(t)=u(t)-u(t-T)$

### Tren de pulsos
![[tren de pulsos.png]]

$x(t)=p(t-0)-p(t-T)-p(t-2T)+p(t-3T)$

### Delta de Dirac
Este modelo matemático, $\delta(t)$ se da cuando la amplitud de un pulso rectangular tiende a 0. Se representa como un vector vertical en t=0 de amplitud 1.
![[delta de Dirac.png]]

Propiedades:
+ $\delta(t)=0\ si\ t\ !=0$
+ $\delta(0)=\infty$
+ $\int_{-\infty}^{+\infty} \delta(t) \, dt = 1$
+ Se puede multiplicar por una constante o desplazarse en el tiempo
