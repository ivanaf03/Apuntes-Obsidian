[[Tema 10-Virtualización de servidores]]

## Alta disponibilidad
La alta disponibilidad permite que los sistemas se recuperen de una falla o interrupción para minimizar el tiempo durante el cual los servicios que proporcionan no están disponibles.

En un clúster de servidores, un servidor puede asumir los servicios proporcionados por otro en caso de una falla. En un clúster de hipervisores, la máquina virtual que se ejecuta en un hipervisor se reiniciará en otro si el hipervisor en el que está en ejecución falla.

En este proceso:
+ Los nodos en el clúster se monitorean entre sí. Los nodos reconocen eventos de falla en el clúster.
+ Los procedimientos y reglas de reinicio definen el orden y la ubicación de las máquinas virtuales reiniciadas.
+ Los nodos deben estar configurados para reconocer y responder al aislamiento.
+ El almacenamiento compartido es crucial. Se requieren configuraciones de red comunes.
+ Debe haber suficiente capacidad de reserva disponible. 
+ La gestión del clúster debe haber configurado la Alta Disponibilidad (HA) y los comportamientos deseados ante fallos.

### Beneficios
+ Reinicio automatizado de cualquier servicio sin intervención del administrador. 
+ No requiere soluciones personalizadas ni hardware de agrupación dedicado para cada solución.
+ El nivel de resiliencia se puede ajustar para proporcionar una protección mejorada, por ejemplo, durante el mantenimiento.

## Tolerancia a fallos
Alta disponibilidad no serviría, por ejemplo, para un hospital. Para ello se creo fault tollerance. Si se cae un server no pasa nada porque otra máquina tendría el estado de memoria copiado.

Se basa en copiar el estado de memoria tras cada operación. Se ejecutan dos instancias completamente sincronizadas de una máquina virtual en dos hipervisores distintos. Si falla un hipervisor o una máquina virtual, la otra continúa proporcionando el servicio. No se experimenta tiempo de inactividad.

Para poder hacerlo: 
+ Se debe utilizar almacenamiento compartido, ya que la máquina virtual se ejecuta simultáneamente en hipervisores separados.
+ El almacenamiento para los archivos de la máquina virtual debe estar conectado a ambos hipervisores.
+ Conexión de red confiable y de alta capacidad de ancho de banda.
+ Capacidad de CPU y RAM.
+ Las máquinas virtuales están limitadas a uno o dos CPU virtuales.

La tolerancia a fallos inicia una máquina virtual y luego pone en marcha la segunda instancia. El proceso de sincronización garantiza que el estado del procesador y la memoria de ambas máquinas virtuales permanezcan sincronizados.

