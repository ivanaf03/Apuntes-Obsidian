[[Tema 1-Modelado de procesos con BPMN]]

El evento de inicio abstracto solo señala que el proceso empieza ahí cuando se inicia una instancia. Todo proceso tiene al menos un evento de inicio y, si tiene más, tienen que ser compatibles entre sí.  Solo puede haber uno, ya que no se sabe sino cual es el primero.

El temporal arranca cuando se cumpla la condición temporal, ya sea una fecha o una periodicidad. Se puede combinar un abstracto con uno o varios temporales.

Una señal es una herramienta de comunicación entre procesos. 

Los eventos intermedios asociados a tareas se pueden usar, por ejemplo, cuando un proceso tiene cierta duración. Por ejemplo, si un coche no está fabricado y tiene que venir de fábrica se pueden modelar así las notificaciones que te van enviando. 

Una excepción se puede capturar y tratar, como un try catch.

Si ocurre un error no recuperable y han ocurrido cambios confirmados no es tan sencillo como deshacer con un rollback. 

La colaboración ocurre cuando dos procesos colaboran entre sí. Ocurre cuando actividades de otro proceso envían datos que necesitan otros procesos. Por ejemplo, cuando un proceso es diferente desde el punto de vista del cliente y del equipo de backend. Por ejemplo, en contratación de telecomunicaciones. 

Inicio -> Registrar pedido -> Perfil riesgo cliente -> Lista morosos (puede acabar ahí) -> Firma contrato -> Fin

Provisión servicios -> (flujo complejo) -> Fin

Un ejemplo es cuando se firma el contrato, esa información puede ser necesaria por algún proceso de abajo. La notación es una línea discontinua con punta de flecha hueca y que inicia con un círculo. La actividad de partida tiene un sobre negro y la que recibe un sobre blanco. 