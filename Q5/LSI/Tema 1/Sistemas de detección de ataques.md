[[Tema 1-Categorías de ataques]]

### Sistemas de detección de ataques
##### IDS (Intrusion Detection System)
Se encarga de detectar actividades anómalas o potencialmente dañinas en una red o sistema. Funciona observando el tráfico de la red o los registros de eventos en busca de patrones de datos o comportamientos que coincidan con amenazas conocidas o reglas previamente definidas. Cuando detecta algo sospechoso, genera una alerta para notificar a los administradores de seguridad, quienes pueden investigar la situación y tomar medidas apropiadas.
##### IPS (Intrusion Prevention System)
A diferencia de un IDS, un IPS no solo detecta las amenazas, sino que también toma medidas activas para prevenirlas o detenerlas. Cuando un IPS detecta una actividad maliciosa o inusual, puede tomar medidas automáticamente para bloquear la amenaza. Esto puede incluir la eliminación de paquetes maliciosos, la desconexión de conexiones sospechosas o la aplicación de políticas de seguridad adicionales para mitigar el riesgo.
##### Sensores IPS (Intrusion Prevention System)
Son componentes específicos dentro de un sistema IPS más grande. Se colocan en puntos estratégicos de una red para supervisar y analizar el tráfico en tiempo real. Por ejemplo, Snort es un software de detección y prevención de intrusiones que utiliza sensores IPS para inspeccionar el tráfico de red en busca de patrones de amenazas y tomar medidas en consecuencia. Estos sensores pueden estar distribuidos en múltiples ubicaciones de la red

### Ubicaciones
+ **A nivel de red:** comprueban el tráfico de red.
+ **A nivel de host:** se encargan de localizar eventos en los logs  para detectar si se ha producido algún ataque o incidente.
