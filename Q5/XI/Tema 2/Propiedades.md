[[Tema 2-Análisis en frecuencia]]

## Propiedad de linealidad
$$\mathcal{F}\{a \cdot x(t) + b \cdot y(t)\} = a \cdot X(\omega) + b \cdot Y(\omega)
$$

Por ejemplo:
![[linealidad 1.png]]![[linealidad 2.png]]

## Escalado en el tiempo
La operación de escalado en tiempo transforma una señal en otra señal donde a es un número real positivo.
+ Cuando a>1 la señal se comprime en tiempo y se expande en frecuencia.
+ Cuando a<1 la señal se expande en tiempo y se comprime en frecuencia.

$$\mathcal{F}\{x(at)\} = \frac{1}{|a|} X\left(\frac{\omega}{a}\right)
$$

Por ejemplo:
![[escalado 1.png]]

## Convolución
$$\mathcal{F}\{x(t) * y(t)\} = X(\omega) \cdot Y(\omega)
$$

Por ejemplo:
![[ejemplo convolucion.png]]
La propiedad de convolución se utiliza en el filtrado.

### Filtro paso bajo ideal
Un filtro paso bajo ideal es un tipo de filtro que permite el paso de frecuencias por debajo de cierta frecuencia de corte y atenúa completamente las frecuencias por encima de esa frecuencia de corte. Para este se utiliza la señal sinc, ya que en dominio de la frecuencia se convierte en un pulso rectangular que delimita frecuencias.

Los pulsos rectangulares son inadecuados para transmitir datos por canales de banda limitada porque al tener un espectro en forma de sinc el canal no permite el paso de todas sus frecuencias.

El canal deforma los pulsos rectangulares y las amplitudes observadas son distintas a las amplitudes transmitidas.


## Multiplicación
$$\mathcal{F}\{x(t) \cdot y(t)\} = \frac{1}{2\pi} X(\omega) * Y(\omega)
$$
Por ejemplo:
![[multiplicación.png]]

