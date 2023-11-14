[[Tema 5-Cableado estructurado]]

### Tipos de cableado
El principal motivo por el que no usamos fibra óptica para todo hoy en día el el coste. Por eso existen todavía otros tipos de cableado:
+ Par trenzado
+ Cable de pares (no están trenzados)
+ Fibra óptica

Según la estructura dividimos el cableado en:
+ Horizontal: conexiones dentro de una misma planta. Suele ser de par trenzado, ya que se conectan terminales de usuario.
+ Vertical: conexiones entre plantas mediante un único nodo en estrella. Suele estar hecho con fibra óptica, ya que el número de datos que se transfieren entre plantas suele ser elevado. Hay una excepción, el cableado de la telefonía.
+ Campus: conexiones entre edificios, por ejemplo, facultades. Suele utilizarse fibra óptica.
+ Usuario: conexión de dispositivos como computadoras, impresoras, teléfonos, cámaras, dispositivos de red y otros equipos de usuario final a la red de datos o la red de comunicación de una organización. Suele utilizarse par trenzado.

### Cables de par trenzado
Está formado por dos hilos conductores cubiertos por un aislante y entrelazados. El trenzado sirve para reducir las interferencias con respecto a los cables cercanos, es decir, la diafonía. Existen 3 tipos:
+ UTP: no tienen apantallamiento, es decir, no tiene una capa que proteja a los conductores internos de interferencias electromagnéticas o radiofrecuencias.
+ FTP: la pantalla exterior cubre todos los cables.
+ STP: una pantalla por cada par.

##### Tipos de cables
+ 5e (100 MHz): máximo 1 Gb
+ 6 (250 MHz): máximo 1 Gb
+ 6A (500 MHz): máximo 10 Gb
+ 7 (600 MHz): máximo 10 Gb
+ 7A (1000 MHz): máximo 10 Gb
+ 8 (2000 MHz): máximo 40 Gb

##### Tipos de conectores
+ RJ11: telefonía analógica
+ RJ12: telefonía analógica
+ RJ45: ethernet

##### Tipos de puerto en los switch
+ RJ45
+ GBIC
+ SFP

##### Medios de transmisión
| Cuestiones de implementación | Medios de cobre |
|-----------------------------|-----------------|
| Ancho de banda admitido     | 10 Mbps a 40 Gbps |
| Distancia (sin repetidores) | Relativamente corta (1 a 100 metros) |
| Inmunidad a EMI y RFI      | Bajo |
| Costes de medios y conectores | Valor más bajo |
| Habilidades de instalación requeridas | Valor más bajo |
| Precauciones de seguridad   | Valor más bajo |


### Fibra óptica
El cable es de cristal y plástico. Se compone de núcleo, revestimiento y cubierta. El problema es que es muy caro. Nos da un ancho de banda superior a 1 GHz. 

....

##### Tipos de conectores
+ Conectores ST
+ Conectores SC
+ Conectores LC
+ Conectores LC multimodo dúplex

##### Tipos de puertos en los switch
+ GBIC
+ SFP

##### Medios de transmisión
| Cuestiones de implementación | Fibra óptica |
|-----------------------------|-------------|
| Ancho de banda admitido     | 10 Mbps a 400 Gbps |
| Distancia (sin repetidores) | Relativamente larga (1 a 50 Km) |
| Inmunidad a EMI y RFI      | Alto (Totalmente inmune) |
| Costes de medios y conectores | Valor más alto |
| Habilidades de instalación requeridas | Valor más alto |
| Precauciones de seguridad   | Valor más alto |
