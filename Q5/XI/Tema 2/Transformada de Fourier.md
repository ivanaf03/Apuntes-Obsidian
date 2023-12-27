[[Tema 2-Análisis en frecuencia]]

## Ecuación de análisis y ecuación de síntesis
La ecuación de análisis, también llamada transformada de Fourier, permite representar una señal en dominio del tiempo a dominio de la frecuencia. X($\omega$) se conoce como espectro de x(t). Se calcula como:

$$X(\omega) = \int_{-\infty}^{\infty} x(t) \cdot e^{-j\omega t} \, dt$$
o, para obtener el resultado en Hz en lugar de en rad/s:
$$X(\omega) = \int_{-\infty}^{\infty} x(t) \cdot e^{-jf2\pi t} \, dt$$

La transformada de Fourier inversa de una función X($\omega$) se denota como x(t) y se expresa de la siguiente manera:
$$x(t) = \frac{1}{2\pi} \int_{-\infty}^{\infty} X(\omega) \cdot e^{j\omega t} \, d\omega$$


## Tranformadas de señales básicas
### Pulso rectangular
La señal:
$$ x(t) = \begin{cases} 1 & \text{si } -\frac{T}{2} \leq t \leq \frac{T}{2} \\ 0 & \text{en otro caso} \end{cases} $$
Se transforma en:
$$
X(\omega) = 2A \cdot \frac{\sin\left(\frac{T\omega}{2}\right)}{\omega}
$$
![[fourier p rectangular.png]]

### Señal sinc
La señal:
$$
\text{sinc}(t) = \frac{\sin(W t)}{\pi t}
$$

Se transforma en:
$$ X(\omega) = \begin{cases} 1 & \text{si } -W \leq \omega \leq W \\ 0 & \text{en otro caso} \end{cases} $$

![[fourier sinc.png]]

### Señal coseno
La señal:
$$ x(t) = \cos(\omega_0 t) $$
Se transforma en:
$$ X(\omega) = \pi \left( \delta(\omega - \omega_0) + \delta(\omega + \omega_0) \right) $$

![[fourier coseno.png]]

## Desplazamientos en tiempo y frecuencia
Si desplazamos en el tiempo una señal senoidal obtenemos una fase ([[Señales|ver tema 1]]):
$$A + \cos(\omega(t - t_0))=$A + \cos(\omega t+ \Phi)$$

La transformada de Fourier de un desplazamiento en el tiempo se traduce en frecuencia como:
$$x(x-t_0)\ se\ transforma\ en\  X(\omega) \cdot e^{-j\omega t_0}
$$

La transformada de un desplazamiento en frecuencia es:
$$e^{\pm j\omega_0 t}se\ tranforma\ en\ X(\omega \mp \omega_0)$$
