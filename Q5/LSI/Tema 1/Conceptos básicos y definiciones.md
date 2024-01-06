[[Tema 1-Categorías de ataques]]

## Seguridad de la información
La seguridad de la información incluye la protección de la confidencialidad, integridad y disponibilidad de la información, independientemente de si está en formato digital o en papel. Implica la gestión y protección de la información en todas sus formas para garantizar que solo las personas autorizadas tengan acceso a ella, que no se altere de manera no deseada y que esté disponible cuando sea necesario.

### Pilares de la seguridad de la información (CIA)
+ **Confidencialidad:** Restricción del acceso a la información a personas no autorizadas.
+ **Integridad:** Capacidad de que los datos no se modifiquen o corrompan.
+ **Disponibilidad:** Accesibilidad a la información cuando esta sea necesaria.

### Seguridad informática
Dentro de la seguridad de la información tenemos la seguridad informática. Esta es el conjunto de prácticas y medidas para proteger sistemas, redes y datos de amenazas cibernéticas y accesos no autorizados.

## Vulnerabilidades
Una vulnerabilidad es una debilidad de un activo o control que puede ser explotada por una amenaza. Los activos son elementos o recursos que tienen cierto valor para una organización. Las medidas implementadas para protegerlos se denominan controles. Por ejemplo:
+ Defectos en hardware o software.
+ Carencia de políticas y procedimientos, como falta de formación a los usuarios.

La finalidad de la ciberseguridad es detectar vulnerabilidades e intentan arreglarlas mediante el parcheo.
### Exploit
Un exploit es es la herramienta o técnica que un atacante utiliza para aprovechar una vulnerabilidad en un sistema.

### Vulnerabilidades críticas
Una vulnerabilidad crítica es una debilidad o fallo en un sistema, aplicación, servicio o dispositivo que representa un riesgo significativo y grave para la seguridad y la integridad de la información. Algunos ejemplos son:
+ shellshock
+ hearthbleed
+ poodle
+ meltdown
+ spectre
+ krack attacks

### Vulnerabilidades Zero-day
Las vulnerabilidades Zero-day son aquellas que aunque son conocidas, todavía no existen parches que las solucionen. Para intentar arreglarlo se suelen tomar pequeñas medidas como cerrar el servicio que lo causa, pausar una conexión momentáneamente, etc. Ocurren cuando:
+ Los desarrolladores no han tenido días para parchear la vulnerabilidad
+ El vendedor no ha propuesto un parche oficial
+ Los administradores no han tenido tiempo para protegerse de la vulnerabilidad

Una vez el parche está disponible dejan de llamarse Zero-day.

## Amenazas
Una amenaza es una posibilidad de violación de la seguridad, que existe cuando se da una circunstancia, capacidad, acción o evento que pudiera romper la seguridad y causar perjuicio. Es decir, una amenaza es un peligro posible que podría explotar una vulnerabilidad. Algunos ejemplos son:
+ reverse trojan
+ time bomb
+ bots
+ keyloggers
+ sniffers
+ backdoors
+ rootkits
+ virus
+ worms
+ spyware
+ troyanos

## Ataques
Un ataque es un asalto a la seguridad del sistema, derivado de una amenaza inteligente, es decir, un acto inteligente y deliberado para eludir los servicios de seguridad y violar la política de seguridad de un sistema.

Por ejemplo:
+ fuerza bruta
+ poisoning 
+ DoS (Denial of Service)
+ CSRF (Cross-Site Request Forgery)
+ XSS (Cross-Site Scripting)
+ inyecciones
+ MITM (Man-In-The-Middle)
+ session hijacking attack
+ sniffing attack

## Otros conceptos importantes
+ **CVE (Common Vulnerabilities and Exposures):** lista de vulnerabilidades conocidas cuyo id acompañado de una descripción. Estas se utilizan en la NVD (National Vulnerability Database). No contiene información sobre cómo corregir las vulnerabilidades o detalles técnicos, esto se encuentra en la NVD.

+ **CVSS (Common Vulnerability Score System):** ranking de valores del 1 al 10 los cuales indican cómo de peligrosa es una vulnerabilidad.

+ **CWE (Common Weakness Enumeration):** lista desarrollada por la comunidad de puntos débiles comunes de seguridad de software y hardware que sirve como lenguaje común, como vara de medir para las herramientas de seguridad y como base para la identificación de puntos débiles, la mitigación y los esfuerzos de prevención.

+ **CPE (Common Platform Enumeration):** iniciativa que permite identificar con un nombre único y estándar los sistemas, plataformas y software de una manera muy detallada.

+ **OVAL (Open Vulnerability and Assessment Language):** estándar abierto y público utilizado para describir y intercambiar información sobre vulnerabilidades de seguridad en sistemas informáticos y redes desarrollado por el NIST (National Institute of Standards and Technology).