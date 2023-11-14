[[Tema 4-Gestión de la configuración software]]

### Definiciones básicas
##### Configuración del software
Es el conjunto de todos los elementos de configuración del software de un proyecto. Es decir, es el conjunto de toda la información y productos utilizados o generados en un proyecto como resultado del proceso de ingeniería del software.

##### ECS (Elemento de configuración del software)
Un ECS es cada uno de los elementos de la configuración del software. Es la unidad de trabajo de la GCS. Por ello debe ser una unidad en sí mismo, es decir, se tiene que poder definir y controlar de forma separada. Por ejemplo:
+ especificación del sistema
+ diseño preliminar
+ diseño detallado
+ ejecutable
+ manual de usuario
+ plan de pruebas
+ estándares de ingeniería utilizados
+ herramientas CASE
+ documentación de los productos utilizados
+ diseños de bases de datos

El sistema en conjunto también es un ECS, aunque se puede descomponer en varios.

### Línea base
Es un concepto basado facilitar el control de cambios. Antes de rear una línea base se pueden hacer cambios rápidos e informales sobre un ECS, pero una vez establecida se debe aplicar un procedimiento formal para evaluar y verificar cada cambio.

##### Visiones
+ **Desde el punto de vista del proceso:** Es un punto de referencia en el proceso de desarrollo que queda marcado por la aprobación de uno o más ECS tras una revisión técnica formal.
+ **Desde el punto de vista del producto:** Es un conjunto de ECS revisados y aceptados que sirven como una base para el desarrollo posterior y que se pueden cambiar solo a través de un proceso formal de control de cambios.
