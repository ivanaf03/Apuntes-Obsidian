[[Tema 8-Tácticas de seguridad en software]]
$\space$
## 1.Qué hacen las tácticas de seguridad?
Las tácticas de seguridad se basan en resistir ataques, no en evitarlos. Es muy complicado evitar todos los posibles ataques que pueden hacerse a un sistema. Además, también se orientan a detectarlos, recuperarse de ellos, etc.
$\space$
## 2.Tácticas
Las tácticas se dividen en 3 tipos principalmente:
+ Tácticas de resistencia a ataques
+ Tácticas de detección de ataques
+ Tácticas de recuperación de ataques
$\space$
### 2.1.Resistencia a ataques
Consisten en mitigar los riesgos y reducir el impacto de las posibles amenazas lo máximo posible.
$\space$
#### 2.1.1.Autenticación de usuarios
Consiste en que el interlocutor, que puede ser el usuario o el propio sistema, diga quién dice ser. Se puede hacer mediante contraseñas fuertes, contraseñas de un solo uso, autenticación en dos posos, etc.
$\space$
#### 2.1.2.Autorización de usuarios
Consiste en asegurar que un usuario, al autenticarse, pueda acceder o modificar servicios o datos. Se puede hacer con grupos de usuarios, roles, listas blancas o negras, etc.
$\space$
#### 2.1.3.Confidencialidad de datos
Consiste en el uso de técnicas de cifrado de datos y de la propia comunicación. Por ejemplo, VPNs, SSL, etc.
$\space$
#### 2.1.4.Integridad de datos
Consiste en garantizar la integridad de la información mediante redundancia. Por ejemplo, comparaciones con el checksum de descargables.
$\space$
#### 2.1.5.Exposición limitada
Consiste en distribuir las funcionalidades críticas en diferentes elementos o lugares para que un ataque enfocado en una de ellas no afecte al resto.
$\space$
#### 2.1.6.Limitación de acceso
Consiste en restringir el acceso a recursos a usuarios no autorizados. Normalmente se hace con un buen diseño y configuración de firewalls.
$\space$
## 2.2.Detección de ataques
Consiste en 