[[Tema 1-Fundamentos de la transmisión de señales]]

## Potencia instantánea
Dada una corriente eléctrica que pase por una resistencia, el voltaje se calcula con la ley de Ohm:
$$V=i \cdot R$$

La potencia instantánea en una resistencia es la cantidad de energía eléctrica que se disipa en ella en un momento puntual.
$$P(t)=R \cdot i^2= V \cdot i= \frac{V^2}{R}$$

La potencia instantánea de una señal x(t) es el cuadrado de la propia señal:
$$p(t)=x^2(t)$$

## Energía disipada y potencia en un intervalo
La energía disipada de una señal en un intervalo de tiempo es la cantidad total de energía que se ha convertido en otras formas (generalmente en calor) durante ese intervalo de tiempo debido a la resistencia eléctrica o a algún otro tipo de pérdida en el sistema. por ejemplo, la energía disipada en un intervalo \[-T/2, T/2] se calcula como:
$$E^{T}_x = \int_{-\frac{T}{2}}^{\frac{T}{2}} x^2(t) \, dt$$

La energía es siempre positiva porque $x^2>=0$ siempre. Solo vale 0 si $x(t)=0$. Si la energía de la señal puede ser finita o infinita.

La potencia en un intervalo, $P^T_x$ se calcula como:
$$P^T_x=E^T_x/T= \frac{1}{T} \int_{-\frac{T}{2}}^{\frac{T}{2}} x^2(t) \, dt$$

La potencia media se calcula con el límite cuando T tiende a infinito de la potencia en el intervalo:
$$P_{\text{media}} = \lim_{{T \to \infty}} \frac{1}{T} \int_{-\frac{T}{2}}^{\frac{T}{2}} x^2(t) \, dt$$

Si la señal tiene energía finita, su potencia media es 0. Si la energía es infinita, generalmente tiene potencia media finita; aunque existen señales de energía y potencia media infinitas.

### Pulso rectangular
$$p(t) = \begin{cases} A, & \text{si } -\frac{T_0}{2} \leq t \leq \frac{T_0}{2} \\ 0, & \text{en otro caso} \end{cases}
$$

$$\text{Energía: } E = A^2 \cdot T_0$$

$$\text{Potencia Media: } P_{\text{media}} = \lim_{{T \to \infty}} \frac{A^2 \cdot T_0}{T} = 0$$

### Señal triangular
$$
x(t) = \begin{cases}
\frac{At}{T_0}, & \text{si } 0 \leq t \leq T_0 \\\
0, & \text{en otro caso}
\end{cases}
$$

$$\text{Energía: } E = \int_{0}^{T_0} x^2(t) \, dt = \int_{0}^{T_0} (At)^2 \, dt = A^2 \int_{0}^{T_0} t^2 \, dt = A^2 \cdot \frac{T_0^3}{3}$$

$$\text{Potencia Media: } P_{\text{media}} = \lim_{{T \to \infty}} \frac{1}{T} \int_{0}^{T_0} x^2(t) \, dt = \lim_{{T \to \infty}} \frac{1}{T} \cdot A^2 \cdot \frac{T_0^3}{3} = \lim_{{T \to \infty}} \frac{A^2 T_0^3}{3T} = 0$$

### Señal senoidal
$$x(t)=A*cos(\omega \cdot t)$$

$$\text{Energía: } E= \int_{0}^{T_0} A^2 \cos^2(\omega t) \, dt = \int_{0}^{T_0} A^2 \cdot \frac{1 + \cos(2\omega t)}{2} \, dt$$

$$E = \frac{A^2}{2} \int_{0}^{T_0} 1 \, dt + \frac{A^2}{2} \int_{0}^{T_0} \cos(2\omega t) \, dt$$

$$E = \frac{A^2}{2} \left[t\right]_{0}^{T_0} + \frac{A^2}{4\omega} \left[\sin(2\omega t)\right]_{0}^{T_0}$$

$$E = \frac{A^2}{2} T_0 + \frac{A^2}{4\omega} (\sin(2\omega T_0) - \sin(0))$$
$$E = \frac{A^2}{2} T_0$$

$$\text{Potencia Media: } P_{\text{media}} = \frac{1}{T_0} \cdot E = \frac{1}{T_0} \cdot \left(\frac{A^2}{2} T_0\right) = \frac{A^2}{2}$$

La energía de las señales senoidales es siempre infinita. La potencia media de una señal periódica es la potencia media de un periodo.