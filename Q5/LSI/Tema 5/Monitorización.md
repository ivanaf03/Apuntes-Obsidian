[[Tema 5-DoS y monitorización]]

## Aircrack
https://www.seguridadwireless.net/manual-aircrack-ng/
+ **aerodump-ng mon0:** captura de paquetes en el canal 0 de una interfaz de red inalámbrica que se ha configurado en modo de monitor

802.11w es un estándar de autenticación y cifrado para prevenir DoS. También se puede con WIPS.  Dos muy conocidos son Cisco adaptative wireless IPS y Open WIPS-ng.

Owisam es una metodología de seguridad para evaluar redes wifi. 

## Herramientas de monitorización
+ **Acrilic:** Monitoriza la conexión wifi. Muestra el RSSI de cada punto de acceso que localiza. El valor ideal sería el 0. De -40 a -60 es bueno y por debajo de -70 es malo.

En redes Wi-Fi de 2.4 GHz, se utilizan diferentes canales para transmitir datos de manera simultánea sin interferencias excesivas. El espectro de 2.4 GHz está dividido en canales que tienen un ancho de banda de 20 MHz cada uno. En la región de 2.4 GHz, hay disponibles 11 canales en muchos países, aunque la disponibilidad exacta puede variar según la región y las regulaciones locales.

| Canal | Frecuencia (GHz) |
|-------|-------------------|
| 1     | 2.412             |
| 2     | 2.417             |
| 3     | 2.422             |
| 4     | 2.427             |
| 5     | 2.432             |
| 6     | 2.437             |
| 7     | 2.442             |
| 8     | 2.447             |
| 9     | 2.452             |
| 10    | 2.457             |
| 11    | 2.462             |

La banda de 5 GHz también se utiliza para redes Wi-Fi, y ofrece más canales y menos interferencias que la banda de 2.4 GHz. Los canales de la banda de 5 GHz varían según las regulaciones regionales y el estándar Wi-Fi utilizado (por ejemplo, 802.11a, 802.11n, 802.11ac (WiFi 5), 802.11ax (WiFi 6), 802.11b, 802.11g). Suele ofrecer 25 canales de 20 MHz.

| Canal | Frecuencia (GHz) |
|-------|-------------------|
| 36    | 5.180             |
| 40    | 5.200             |
| 44    | 5.220             |
| 48    | 5.240             |
| 52    | 5.260             |
| 56    | 5.280             |
| 60    | 5.300             |
| 64    | 5.320             |
| 100   | 5.500             |
| 104   | 5.520             |
| 108   | 5.540             |
| 112   | 5.560             |
| 116   | 5.580             |
| 120   | 5.600             |
| 124   | 5.620             |
| 128   | 5.640             |
| 132   | 5.660             |
| 136   | 5.680             |
| 140   | 5.700             |
| 144   | 5.720             |
| 149   | 5.745             |
| 153   | 5.765             |
| 157   | 5.785             |
| 161   | 5.805             |
| 165   | 5.825             |

Por ejemplo, el estándar 802.11n puede agrupar 2 canales de 20MHz en un canal de 40MHz.

WiFi 6 tiene modulación de acceso múltiple a división de frecuencias. Por ejemplo si tengo varias máquinas en el canal 1, cuando una máquina transmitía ocupaba todo el canal. Pero en WiFi 6 se divide la frecuencia en ventana más pequeñas por canal. Esto permite que pueda haber varias máquinas transmitiendo a la vez.

## White lists
Un lwhite list es una serie de IPs permitidas. También podemos hacer priorización de tráfico y balanceo de carga. Otra forma es con el uso de TABs.

### Traffic scrubbing
Es un servicio de limpieza de tráfico. Puede hacerse en la nube. Estos funcionan de forma que si detectan ataques DoS, las empresas que lo gestionan enrutan el tráfico hacia ellas y limpian el tráfico antes de reenviártelo.

### Black lists
Real time black lists es una página que comprueba en muchas bases de datos la reputación de la IP que pidas.

Otro proyecto es Spamhaus. SBL (Spamhaus Bloack List) es una lista de IPs de las que no se recomienda aceptar emails. XBL (Exploit Block List) es una lista de IPs de máquinas infectadas. Otras son PBL, DBL (url de empresas que aparecen en mensajes de spam), ZEN...