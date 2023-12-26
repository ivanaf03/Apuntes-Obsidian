[[Tema 2-Análisis en frecuencia]]

## Ecuación de análisis y ecuaión de síntesis
La ecuación de análisis, también llamada transformada de Fourier, permite representar una señal en dominio del tiempo a dominio de la frecuencia. X($\omega$) se conoce como espectro de x(t). Se calcula como:

$$X(\omega) = \int_{-\infty}^{\infty} x(t) \cdot e^{-j\omega t} \, dt$$
o, para obtener el resultado en Hz en lugar de en rad/s:
$$X(\omega) = \int_{-\infty}^{\infty} x(t) \cdot e^{-jf2\pi t} \, dt$$

La transformada de Fourier inversa de una función X($\omega$) se denota como x(t) y se expresa de la siguiente manera:
$$x(t) = \frac{1}{2\pi} \int_{-\infty}^{\infty} X(\omega) \cdot e^{j\omega t} \, d\omega$$


