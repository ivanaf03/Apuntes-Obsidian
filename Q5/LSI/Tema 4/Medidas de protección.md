[[Tema 4-Sniffing]]

## Boundings
Bonding es una técnica que permite combinar varias interfaces de red físicas en una sola interfaz virtual para proporcionar redundancia y/o aumentar el rendimiento. Se hace con el comando ifenslave. Se hace en el fichero /etc/modules con echo>>bounding. Estos modos son:
+ Mode 0 RR
+ Mode 1 Active-backup
+ Mode 2 XOR
+ Mode 3 Broadcast
+ Mode 4 802.3 AD
+ Mode 5 Balance-TLB
+ Mode 6 Balance-ALB

En el fichero interfaces:
```
iface bound inet static
adress x.x.x.x
...
slaves ens33 ens34 ens35
bound_mode 0  # Para Round Robin
```

## DHCP snooping
Se utiliza para mitigar ataques de suplantación de DHCP (Dynamic Host Configuration Protocol). El protocolo DHCP se utiliza para asignar direcciones IP de manera dinámica a dispositivos en una red, como computadoras y dispositivos móviles. Sin embargo, si un atacante se hace pasar por un servidor DHCP falso, podría asignar direcciones IP maliciosas a dispositivos y comprometer la seguridad de la red.

## Port security
Por defecto permite solo una MAC asociada a cada puerto y el modo shutdown, si se produce una vulneración en ese puerto tira la paquetería y deshabilita el puerto.
```
switchl port-security maximum 4
```

```
switchl port-security mac-address xx:xx..:xx
```

```
switchl port-security violation protect (o violation restrict)
```

## TAP
Los Test Access Ports son dispositivos que se suelen montar entre los router y firewall. Permite la monitorización del tráfico de red en tiempo real sin afectar el flujo normal de datos. Los TAPs pueden utilizarse para la depuración de redes, el análisis del tráfico, la monitorización de la seguridad y otras tareas de diagnóstico.

## Firewall de nueva generación
Tienen WAT, hipervisores para virtualizar todas las máquinas. Trabajan a todos los niveles e incluyen sistemas de prevención de intrusiones. Están vinculados a los sistemas de autenticación. Pueden analizar el tráfico en busca de malware. Suelen cortar el cifrado. 

Empresas de firewalls de palo alto:
+ Cisco
+ Jupiter
+ Checkpoint

## SIEM (Sistemas de Gestión de Eventos)
Por ejemplo, splunk, prelude, arcsight, logrytm... Por ejemplo, el del CESGA está montado con Apache Hadoop. Se suelen usar sistemas de ficheros distribuidos, como HSFS, y modelos de programación, como map reduce. Los SOC están vinculados al SIEM, que trabajan con logs. A mayores también están vinculados a EDR, que trabajan con agentes. Sirven para securizar hosts finales.

## SORBS (Spam and Open Relay Blocking System)
Es un servicio y una base de datos que se utiliza para identificar y bloquear servidores de correo electrónico que pueden ser utilizados para enviar correo basura (spam) o que presentan vulnerabilidades de retransmisión abierta. Fue creado para ayudar a las organizaciones y proveedores de servicios de Internet (ISPs) a reducir la cantidad de correo no deseado que llega a sus usuarios y prevenir el abuso de servidores de correo.

