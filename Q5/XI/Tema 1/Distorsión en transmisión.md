[[Tema 1-Fundamentos de la transmisión de señales]]

## Modelo de un sistema de comunicación digital
Un sistema de comunicación digital es un conjunto de dispositivos y técnicas que se utilizan para transmitir, procesar y recibir información en formato digital. La información digital se representa mediante secuencias discretas de bits.
![[sistema digital.png]]

Está formado por:
+ **Fuente de información:** genera bits.
+ **Modulador:** asigna forma de onda a los bits.
+ **Canal:** medio a través del cual se transmite la información. Introduce distorsiones a la señal.
+ **Detector:** demodula para recuperar la información original en formato binario.

## Pulse Amplitude Modulation
PAM es una modulación digital. El número de señales del modulador, M, se obtiene mediante el número de bits como:
$$M=2^b$$

Un señal se obtiene cambiando la amplitud de un pulso p(t). La amplitud se obtiene como:
$$A_{i}=M-2 \cdot i -1$$

Por tanto:
$$s_i(t) = A_{i} \cdot p(t)$$

La velocidad o frecuencia de símbolo es la velocidad de bit entre el número de bits que se transmiten en cada símbolo:
$$v_s=1/T=v_b/b$$

### 2-PAM
Para M=2:

+ i=0, por tanto, A=2-2\*0-1=1, s0(t)=p(t)
+ i=1, por tanto, A=2-2\*1-1=-1, s1(t)=-p(t)

![[2pam.png]]
![[2pam 2.png]]

### 4-PAM
Para M=4:

+ i=0, por tanto, A=4-2\*0-1=3, s0(t)=3p(t)
+ i=1, por tanto, A=4-2\*2-1=1, s1(t)=p(t)
+ i=2, por tanto, A=4-2\*4-1=-1, s0(t)=-p(t)
+ i=3, por tanto, A=4-2\*6-1=-3, s1(t)=-3p(t)

![[4pam.png]]
![[4pam 2.png]]

## Distorsión
### Atenuación
La atenuación es la pérdida de potencia que se produce en el medio de transmisión por la separación entre transmisor y receptor. Se calcula como:
$$G=P_{entrada}/P_{salida}$$

Se expresa en Watios (W). En medios guiados se suele expresar en dB/km. En medios no guiados influyen las condiciones atmosféricas además de la distancia.

$$G_{db}=10 \cdot log_{10}G$$

Algo frecuente es utilizar el dBm, donde $P_{salida}$ es 1 mW.

### Retardos
Pueden ser de dos tipos:
+ **De