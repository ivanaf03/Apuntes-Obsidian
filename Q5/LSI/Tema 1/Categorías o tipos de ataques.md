[[Tema 1-Categorías de ataques]]

## Ataques pasivos
El atacante intenta recaudar información del sistema, sin afectar a los recursos del mismo. Se hacen en las transmisiones y son muy difíciles de detectar, por eso se debe dar más importancia a la prevención, por ejemplo, con el cifrado, que a la detección. Aunque pese a estar cifrado, un atacante puede obtener información útil como la localización e identidad de los servidores que se comunican y descubrir la frecuencia y la longitud de los mensajes.

### Ataques de Intercepción (Interception)
Se centran en la captura no autorizada de datos en tránsito. Los atacantes interceptan y escuchan la comunicación entre dos partes para robar información confidencial, como contraseñas, datos financieros o mensajes de correo electrónico. Los ataques de tipo Man-in-the-Middle (MitM) son un ejemplo común de este tipo de ataque.

## Ataques activos
El atacante trata de alterar recursos del sistema o el funcionamiento del mismo. Son opuestos a los ataques pasivos, el objetivo es tratar de detectarlos y recuperarse de ellos.

Los ataques pueden ir al origen, al flujo o al destino del objetivo. Es importante tener bien protegido todo, ya que si nos centramos en una sola parte los ataques van a ir destinos ahí.

### Ataques de Interrupción (Denial of Service - DoS)
Un atacante intenta sobrecargar un sistema o servicio para que se vuelva inaccesible para los usuarios legítimos. Esto se logra inundando el sistema con una gran cantidad de solicitudes o tráfico malicioso, agotando los recursos disponibles o explotando vulnerabilidades para bloquear el acceso. Son ataques con detección inmediata. Por ejemplo: ataques al hardware, como robos; borrados de bases de datos o ficheros; DDoS con botnets o Dos... Existen dos tipos de ataques DoS:
+ **Lógicos:** ataques a puntos concretos vulnerables.
+ **Inundaciones:** Se basan en saturar el servidor a base de establecer las conexiones. Para frenarlas podríamos cerrar las IPS de las que se reciben muchas peticiones. Sin embargo, existen los proxys,  unos equipos informáticos que interceptan conexiones de red hechas desde un cliente a un servidor de destino. Un ejemplo de software que se suele montar en los proxys es squid. Estos servidores hacen que todo salga a la red con la misma IP,  por lo que limitando en el servidor destino el numero de conexiones desde la misma IP, estarías cortando conexiones legales.  El traffic shaping es un mecanismo de control de ancho de banda del tráfico inyectado a la red. Su objetivo es evitar una posible sobrecarga en redes mal dimensionadas, con altas ráfagas de tráfico inyectado. En IPs con QoS es necesario especificar el perfil de tráfico en una conexión para decidir cómo asignar los distintos recursos de la red. El truco está en disminuir el ancho de banda de aquellas conexiones que no sabemos al 100% si son malas.

### Ataques de Modificación (Modification) 
Aquí, los atacantes alteran los datos o la información transmitida entre dos puntos sin ser detectados. Pueden modificar datos para su propio beneficio o para dañar la integridad de la información. Un ejemplo es la modificación de un archivo adjunto en un correo electrónico antes de que llegue a su destinatario. Es un ataque contra la integridad (con funciones hash). Por ejemplo: keyloggers, modificación de mensajes, buffer-overflow, email-fake, sms-fake... Un ejemplo importante es el spoofing consiste en suplantar algo, como una MAC, por ejemplo. 

### Ataques de Generación (Fabrication)
Los atacantes crean y envían datos falsificados o no autorizados a un sistema o red. Esto puede incluir la creación de identidades falsas, registros de acceso falsificados o paquetes de datos fraudulentos. El objetivo puede ser engañar a un sistema para que tome decisiones basadas en información falsa. Son ataques contra la autenticidad. Por ejemplo, mensajes de email falsos, virus, spyware, modificación de dns... Podemos usar herramientas como scapy, packit, o hping3 para hacer este tipo de ataques.

