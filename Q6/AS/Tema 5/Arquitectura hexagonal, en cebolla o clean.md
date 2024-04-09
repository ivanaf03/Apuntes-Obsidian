[[Tema 5-Otras arquitecturas emergentes]]

## 1.Motivación
Uno de los grandes problemas de las aplicaciones es combinar la lógica de negocio con la interfaz de usuario. Complica:
+ Las pruebas.
+ El uso de otros programas.
+ El cambio de uso de la aplicación.

## 2.Solución
La arquitectura hexagonal permite separar la aplicación en capas aisladas por responsabilidades que faciliten la reutilización.

![[arquitectura hexagonal.png]]

### 2.1.Definición de la arquitectura
Antes se llamaba patrón puertos-adaptadores. Propone que el dominio sea el núcleo de las capas y que no se acople a nada externo mediante el principio de inversión de las dependencias.

Todas las capas son punto único de fallo.