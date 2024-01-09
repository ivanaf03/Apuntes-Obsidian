[[Interfaces Persoa Máquina]]

## Tipos de pruebas
Fuente: https://www.anayarojo.net/blog/post/2/que-son-las-pruebas-end-to-end-y-como-llevarlas-a-cabo
![[pruebas en aplicaciones.png]]

+ **Pruebas unitarias:** permiten probar los elementos más fundamentales del software como objetos, funciones, eventos, etc.
+ **Pruebas de componentes:** permiten identificar fallas en componentes que incluyen varias funciones o elementos internos.
+ **Pruebas de integración:** permiten probar el comportamiento y posibles fallas en la interacción entre los componentes entre sí, y demás elementos del software.
+ **Pruebas end2end:** permiten identificar fallas en la interfaz de usuario. Es el testing más elaborado que existe, porque depende de los demás niveles.

### Pruebas end2end
Es una metodología de pruebas de software que consiste en probar una aplicación desde el punto de vista del usuario final. En este tipo de pruebas se prueban los flujos y procesos.

Aunque end to end testing no sustituye ninguna otra de las pruebas, como unit, components o integration testing, esta metodología ofrece el punto de vista del usuario final. Por tanto, nos permite identificar errores en el interfaz del usuario.

Un ejemplo en mi aplicación de flutter (prueba funcionalidad añadir divisa):
+ El driver comprueba que existe un botón con el símbolo de "+".
+ Pulsa el botón.
+ El driver comprueba que existe un botón para seleccionar EUR.
+ Pulsa EUR.
+ El driver comprueba que hay en la pantalla de inicio un campo con la conversión en EUR.