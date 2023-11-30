[[Tema 7-Virtualización de red]]

### Concepto
En las redes convencionales el plano de control y el plano de datos van unidos. El plano de control se encarga de tomar decisiones sobre cómo deben fluir los datos en la red, mientras que el plano de datos se encarga de la transferencia real de esos datos siguiendo las instrucciones del plano de control.

El principal objetivo de las SDN es simplificar la creación y administración de red separando estos dos planos. Se suele utilizar en centros de datos y por los IPS.

### Arquitectura
Las SDN están formadas por dos capas, la capa norte y la capa sur, separadas por un controlador SDN.

1. **Plano de Control (Control Plane):**
    - **Controlador SDN:** En el corazón de la arquitectura SDN se encuentra el controlador, que es un software centralizado. El controlador es responsable de tomar decisiones de enrutamiento y gestión de la red. A través de interfaces de programación, el controlador puede comunicarse con dispositivos en la red para instruir sobre cómo manejar el tráfico.
    - **Interfaz norte (Northbound Interface):** Es la interfaz a través de la cual el controlador se comunica con las aplicaciones y servicios que desean utilizar la red. Proporciona una abstracción de alto nivel para que las aplicaciones puedan especificar sus necesidades de red.
2. **Plano de Datos (Data Plane):**
    - **Dispositivos de red (Switches y routers):** El plano de datos contiene los dispositivos de red, como switches y routers. Estos dispositivos se comunican con el controlador SDN y toman decisiones de transferencia de datos basadas en las instrucciones proporcionadas por el controlador.
    - **Interfaz sur (Southbound Interface):** Es la interfaz a través de la cual el controlador se comunica con los dispositivos de red en el plano de datos. Proporciona una abstracción para que el controlador pueda instruir a los dispositivos sobre cómo manejar el tráfico.
3. **Capa de Abstracción (Abstraction Layer):**
    - **Capa de abstracción de red:** Proporciona una vista unificada de la red y sus recursos. Esta capa facilita la gestión de la red al abstraer la complejidad subyacente y permitir una administración más sencilla y eficiente.
4. **Aplicaciones y Servicios:**
    - **Aplicaciones SDN:** Estas son las aplicaciones y servicios que aprovechan la flexibilidad y la programabilidad de la red definida por software. Pueden ser aplicaciones de gestión de tráfico, seguridad, optimización de recursos, entre otras.

### Características
+ Conmutación a nivel 2
+ Enrutamiento a nivel 3 dinámico y distribuido
+ Balanceo de carga
+ VRF (Virtual Routing and Forwarding)
+ Firewalls distribuidos de capa 2 a 7
+ Seguridad a nivel de usuario, sesión o aplicación
+ Gateway con la red física
+ VPN
+ Sistemas de seguridad avanzados

### Ventajas
+ **Flexibilidad:** despliegue de servicios, aplicaciones e infraestructuras.
+ **Innovación:** creación de nuevos tipos de aplicaciones, protocolos y modelos de negocio.
+ **OPEX:** sencillez de configuración y gestión, reducción de tiempo de administración y reducción de posibles errores
+ **CAPEX:** ampliación de la vida útil de los equipos y reducción del número de estos

Una desventaja es que es todo demasiado dependiente del controlador, aunque se pueden tener varios en la misma red.

### Controladores
+ Open Source:
	+ OpenDaylight
	+ Onos
+ Comerciales:
	+ Cisco Application Centric Infraestructure
	+ Vmware NSX
	+ Juniper Contrail
	+ Nuage Networks VSP