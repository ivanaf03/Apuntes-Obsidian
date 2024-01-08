[[Tema 1-Fundamentos de la transmisión de señales]]

## ¿Qué es el multitrayecto?
El multitrayecto ocurre cuando las ondas se reflejan, refractan o difractan al encontrar obstáculos en su camino entre el transmisor y el receptor. 

En entornos urbanos, edificios, montañas u otros obstáculos pueden causar que las ondas se reflejen en diferentes direcciones, llegando al receptor en múltiples trayectorias. Las señales que llegan por trayectorias diferentes pueden interferir entre sí de manera constructiva o destructiva, lo que puede afectar la calidad de la señal recibida.

Para saber el comportamiento del sistema se aplica $\delta(t)$ a la respuesta al impulso h(t):
![[delta a la salida.png]]

La salida, y(t), se calcula como la convolución de la entrada y la respuesta al impulso:
$$y(t) = x(t)*h(t)= \int_{-\infty}^{\infty} x(\tau) \cdot h(t - \tau) \, d\tau$$

## Convoluciones
La convolución es un concepto matemático y una operación que combina dos funciones para producir una tercera función que describe cómo una cantidad particular evoluciona en respuesta a la influencia de otra.

Las propiedades son:
+ **Elemento neutro:** $x(t) * 0 = 0$
+ **Elemento unitario:** $x(t) * \delta(t) = x(t)$
+ **Conmutativa:** $x(t) * y(t) = y(t) * x(t)$
+ **Asociativa:** $x(t) * (y(t) * z(t)) = (x(t) * y(t)) * z(t)$
+ **Distributiva con respecto a la suma:** $x(t) * (y_1(t) + y_2(t)) = x(t) * y_1(t) + x(t) * y_2(t)$

Un ejemplo:
![[conv1.png]]
![[conv2.png]]
![[conv 3.png]]

### Ejercicio 1
![[ejercicio conv1.png]]

### Ejercicio 2
![[ejercicio 2 conv.png]]

### Convolución de dos pulsos rectangulares
![[conv rect 1.png]]![[conv rect 2.png]]
![[conv rect 3.png]]
![[conv rect 4.png]]

### Ejercicio 3
![[ejercicio conv 3.png]]