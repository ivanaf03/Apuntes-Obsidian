[[Tema 7-Virtualización de red]]

## Network Functions Virtualization
Se basa en la substitución de hardware por software. Uno de los mayores problemas al principio era la seguridad. Además como la industria de redes sigue unos estándares muy concretos y en muchos casos tiene dependencias de hardware.

La NFV permite implementar las funciones de red por software en lugar de hardware para evitar dispositivos hardware. Se utilizan máquinas virtuales sobre servidores estándar, equipos de red o infraestructuras en la nube para proporcionar los mismos servicios que los dispositivos.

### Cadenas de servicios
Las cadenas de servicios (Service Function Chaining, SFC) son un enfoque en redes que permite especificar y orquestar el flujo de tráfico de red a través de una serie predefinida de funciones de servicio. En lugar de simplemente enviar paquetes de datos de un punto a otro en la red, las cadenas de servicios permiten que los paquetes sigan un camino específico, pasando por funciones de red designadas para realizar tareas específicas.

### Ventajas
+ Simplifica la red.
+ Mejora la escalabilidad de la red y permite independencia de los fabricantes.
+ Reduce el Time to market ( tiempo que transcurre desde el inicio del desarrollo de un producto o servicio hasta que está disponible para su venta o uso en el mercado).
+ Permite alta disponibilidad del servicio.
+ Reduce el CAPEX y el OPEX para los operadores (gastos).
+ El retorno de las inversiones es mucho más rápido.

### Soluciones comerciales
+ Cisco One
+ HP
+ Microsoft
+ IBM
+ Google
+ Dell
+ VMWare

### IaaS
Las plataformas IaaS (Infraestructura como Servicio) son un tipo de servicio en la nube que proporciona acceso a recursos informáticos fundamentales, como máquinas virtuales, almacenamiento y redes, a través de internet. Por ejemplo:
+ OpenNebula
	+ Es sencilla.
	+ Permite administrar máquinas virtuales.
	+ Es elástica en cómputo, almacenamiento y servicios.
	+ Es segura.
	+ Tiene HA.
	+ Interconexión y colaboración de múltiples entornos de nube o centros de datos para compartir recursos.
	+ Marketplace.
	+ Tiene un sistema de contabilidad y facturación.
	+ Tiene capacidad para trabajar con diferentes sistemas, plataformas o servicios de nube.
	+ Da una licencia Apache.
+ OpenStack