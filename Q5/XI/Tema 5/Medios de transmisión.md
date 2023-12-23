[[Tema 5-Cableado estructurado]]

## Tipos de cableado
El principal motivo por el que no usamos fibra óptica para todo hoy en día es el coste. Por eso existen todavía otros tipos de cableado:
+ Par trenzado
+ Cable de pares (no están trenzados)
+ Fibra óptica

Según la estructura, dividimos el cableado en:
+ **Horizontal:** conexiones dentro de una misma planta. Suele ser de par trenzado, ya que se conectan terminales de usuario.
+ **Vertical:** conexiones entre plantas mediante un único nodo en estrella. Suele estar hecho con fibra óptica, ya que el número de datos que se transfieren entre plantas suele ser elevado, a excepción del cableado de la telefonía.
+ **Campus:** conexiones entre edificios, por ejemplo, facultades. Suele utilizarse fibra óptica.
+ **Usuario:** conexión de dispositivos como computadoras, impresoras, teléfonos, cámaras, dispositivos de red y otros equipos de usuario final a la red de datos o la red de comunicación de una organización. Suele utilizarse par trenzado.

### Cables de par trenzado
Está formado por dos hilos conductores cubiertos por un aislante y entrelazados. El trenzado sirve para reducir las interferencias con respecto a los cables cercanos, que se conoce como diafonía, y aislar del ruido exterior. Existen 3 tipos:
+ **UTP:** no tienen apantallamiento, es decir, no tiene una capa que proteja a los conductores internos de interferencias electromagnéticas o radiofrecuencias.
+ **FTP:** la pantalla exterior cubre todos los cables.
+ **STP:** una pantalla por cada par.
![[cables de par trenzado.png]]

Se dividen en las siguientes categorías:
+ 5e (100 MHz): máximo 1 Gb
+ 6 (250 MHz): máximo 1 Gb
+ 6A (500 MHz): máximo 10 Gb
+ 7 (600 MHz): máximo 10 Gb
+ 7A (1000 MHz): máximo 10 Gb
+ 8 (2000 MHz): máximo 40 Gb

Los conectores que se usan son:
+ RJ11: telefonía analógica. Tiene 6 posiciones y 4 contactos.
+ RJ12: telefonía analógica. Tiene 6 posiciones y 6 contactos.
+ RJ45: ethernet. Tiene 8 posiciones y 8 contactos.
![[conectores.png]]

En los switches utiliza puertos:
+ RJ45
+ GBIC
+ SFP

### Fibra óptica
La fibra óptica está compuesta principalmente de un núcleo de cristal o plástico rodeado por un revestimiento y una cubierta protectora. La transmisión de datos se logra mediante la transmisión de pulsos de luz a través del núcleo. Es muy cara, pero ofrece un ancho de banda extremadamente alto.

La fibra óptica utiliza señales digitales ópticas unidireccionales, lo que significa que la información se transmite en forma de pulsos de luz en una sola dirección. Además puede admitir múltiples canales de transmisión, lo que permite la transmisión simultánea de información en diferentes longitudes de onda. Esto facilita la transmisión de grandes volúmenes de datos.

Ofrece una excelente relación señal/ruido, lo que significa que la calidad de la señal es alta y la interferencia es mínima. La señal puede viajar distancias significativas sin degradarse demasiado.

Se suele usar en:
+ Transmisiones de larga distancia.
+ Backbones.
+ Trunk lines, conexiones de alta capacidad que interconectan diferentes partes de una red.

Puede ser:
+ **Monomodo (SMF):** 
	+ Produce una única trayectoria recta para la luz.
	+ Núcleo de 9 micrones.
	+ Cubierta de vidrio de 125 micrones de diámetro.
	+ Revestimiento de polímero.
	+ Menor dispersión.
	+ Apto para largas distancias.
	+ Utiliza láseres como fuentes de luz.
	+ Suele utilizarse en backbones de campus de miles de metros.
+ **Multimodo (MMF):** 
	+ Permite varias trayectorias para la luz.
	+ Núcleo de 50 a 62,5 micrones.
	+ Cubierta de vidrio de 125 micrones de diámetro.
	+ Revestimiento de polímero.
	+ Mayor dispersión, por tanto, pérdida de señal.
	+ Apto para largas distancias, pero no tanto como la monomodo.
	+ Utiliza LEDs como fuentes de luz.
	+ Suele utilizarse en LAN o en redes internas de campus.

Los conectores que se usan son:
![[conectores de fibra.png]]
En los switches utiliza puertos:
+ GBIC
+ SFP
![[gbic sfp.png]]

## Cobre vs fibra
| **Cuestiones de implementación** | **Fibra óptica** | **Medios de cobre** |
|-----------------------------|--------------|-----------------|
| Ancho de banda admitido     | 10 Mbps a 400 Gbps | 10 Mbps a 40 Gbps |
| Distancia (sin repetidores) | Relativamente larga (1 a 50 Km) | Relativamente corta (1 a 100 metros) |
| Inmunidad a EMI y RFI      | Alto (Totalmente inmune) | Bajo |
| Costes de medios y conectores | Valor más alto | Valor más bajo |
| Habilidades de instalación requeridas | Valor más alto | Valor más bajo |
| Precauciones de seguridad   | Valor más alto | Valor más bajo |

