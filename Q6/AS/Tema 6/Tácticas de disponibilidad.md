[[Tema 6-Disponibilidad]]
$\space$
## 1.Para que sirven las tácticas de disponibilidad?
Las tácticas de disponibilidad se orientan a evitar que un error se convierta en un fallo. Suelen involucrar mecanismos de monitorización, redundancia y recuperación. 
$\space$
### 1.1.Tácticas
Pueden ser:
+ **De detección de errores:**
	+ **Ping/echo:** un componente envía pings a los demás para comprobar los tiempos de respuesta.
	+ **Heartbeat:** los componentes envían periódicamente señales, por lo que si una señal no llega se da por muerto. A veces se envía información adicional.
	+ **Excepciones:** los componentes lanzan excepciones cuando fallan, que gestionan eles mismos u otros componentes con los que interactúan. Aumenta la complejidad de los componentes y a veces no es posible que un componente conozca sus fallos.
+ **De recuperación de errores:**
	+ **Votación:** se incluyen componentes equivalentes que realizan la misma operación en paralelo y otro componente que decide que solución es mejor. Si uno de los componentes da una solución muy diferente se reinicia. Es muy caro.
	+ **Redundancia activa:** si un componente falla, se usa otro componente que hace lo mismo en paralelo. Es una solución cara.
	+ **Redundancia pasiva:** en un grupo de componentes, un componente responde a los eventos e informa a los demás del resultado. Si falla, otro lo sustituye.
	+ **Repuesto:** tener en componente de repuesto que utilizar en caso de fallo del original. Por ejemplo, checkpoints y backups.
	+ **Operación en la sombra:** un componente controla los fallos y decide que hacer, reiniciarlo, substituirlo, etc.
+ **De prevención de errores:**
	+ **Retirada de servicio:** reiniciar componentes críticos periódicamente para prevenir fallos.
	+ **Transacciones:** agrupar operaciones para podes deshacerlas en conjunto. Evita fallos en la información si un paso falla. Previene colisiones en accesos a la misma información.
	+ **Monitor de procesos:** un proceso supervisa el mal funcionamiento de otros componentes.
