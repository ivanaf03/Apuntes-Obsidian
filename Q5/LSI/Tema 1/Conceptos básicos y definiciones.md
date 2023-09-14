[[Tema 1-Categorías de ataques]]

### Seguridad informática
La seguridad de la información son todas aquellas medidas preventivas y reactivas del hombre, de las organizaciones y de los sistemas tecnológicos que permitan resguardar y proteger la información buscando mantener. Se basa en 3 pilares (CIA):
+ Confidencialidad (*Confidentiality*)
+ Integridad (*Integrity*)
+ Disponibilidad (*Avaliability*)

Dentro de la seguridad de la información está la seguridad informática. Esta se compone por el grupo de herramientas diseñadas para proteger los datos y evitar la intrusión de los hackers.

### Vulnerabilidades
Una vulnerabilidad es una debilidad de un activo o control que puede ser explotada por una amenaza. Un *exploit* es un módulo o programa que explota una vulnerabilidad para ganar privilegios, acceso a determinadas cosas como bases de datos o servicios, etc. Las amenazas son todas esas herramientas que se usan para realizar *exploits*. Hacer esto se conoce como un ataque.

Por ejemplo:
+ Defectos de hardware o software
+ Carencia de políticas o procedimientos

Los profesionales se dedican a detectar vulnerabilidades e intentan arreglarlas mediante el parcheo.

Algunos ejemplos de vulnerabilidades críticas son:
+ *shellshock*
+ *hearthbleed*
+ *poodle*
+ *meltdown*
+ *spectre*
+ *krak attacks*

Las vulnerabilidades Zero-day son aquellas que aunque son conocidas, todavía no existen parches que las solucionen. Para intentar arreglarlo se suelen tomar pequeñas medidas como cerrar el servicio que lo causa, pausar una conexión momentáneamente, etc. Ocurren por:
+ Los desarrolladores no han tenido días para parchear la vulnerabilidad
+ El vendedor no ha propuesto un parche oficial
+ Los administradores no han tenido tiempo para protegerse de la vulnerabilidad

Una vez el parche está disponible dejar de llamarse Zero-day.

### Amenazas
Una amenaza es una posibilidad de violación de la seguridad, que existe cuando se da una circunstancia, capacidad, acción o evento que pudiera romper la seguridad y causar perjuicio. Es decir, una amenaza es un peligro posible que podría explotar una vulnerabilidad.

Por ejemplo:
+ *reverse trojan*
+ *time bomb*
+ *bots*
+ *keyloggers*
+ *sniffers*
+ *backdoors*
+ *rootkits*
+ virus
+ *worms*
+ *spyware*
+ caballos de troya

### Ataques
Un ataque es un asalto a la seguridad del sistema, derivado de una amenaza inteligente; es decir, un acto inteligente y deliberado (especialmente en el sentido de método o técnica) para eludir los servicios de seguridad y violar la política de seguridad de un sistema.

Por ejemplo:
+ fuerzas brutas
+ envenenamientos
+ DoS (*Denial of Service*)
+ CSRF (*Cross-Site Request Forgery*)
+ XSS (*Cross-Site Scripting*)
+ inyecciones
+ *man-in-the-middle*
+ *session hijacking attack*

### Otras definiciones
+ CVE (*Common Vulnerabilities and Exposures*) es una lista de vulnerabilidades conocidas cuyo id acompañado de una descripción. Estas se utilizan en la NVD (*National Vulnerability Database*). No contiene información sobre cómo corregir las vulnerabilidades o detalles técnicos, esto se encuentra en la NVD.

+ CVSS (*Common Vulnerability Score System*) es un ranking de valores del 1 al 10 los cuales indican cómo de peligrosa es una vulnerabilidad.

+ CWE (*Common Weakness Enumeration*) es es una lista desarrollada por la comunidad de puntos débiles comunes de seguridad de software y hardware que sirve como lenguaje común, como vara de medir para las herramientas de seguridad y como base para la identificación de puntos débiles, la mitigación y los esfuerzos de prevención.

+ CPE (*Common Platform Enumeration*) es una iniciativa que permite identificar con un nombre único y estándar los sistemas, plataformas y software de una manera muy detallada.

+ OVAL (*Open Vulnerability and Assessment Language*) es un estándar abierto y público utilizado para describir y intercambiar información sobre vulnerabilidades de seguridad en sistemas informáticos y redes desarrollado por el NIST.