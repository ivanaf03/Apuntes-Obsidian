 [[Enxeñaría de requisitos]]
$\space$
## 2.Sección 8.4.2
La sección 8.4.2 nos da un índice para realizar una especificación de requisitos que se adapte a la norma.
$\space$
### 2.1.índice
1. Introducción
    1.1 Propósito
    1.2 Alcance
    1.3 Resumen del producto
        1.3.1 Perspectiva del producto
        1.3.2 Funciones del producto
        1.3.3 Características del usuario
        1.3.4 Limitaciones
    1.4 Definiciones
2. Referencias
3. Requisitos específicos
    3.1 Interfaces externas
    3.2 Funciones
    3.3 Requisitos de rendimiento
    3.4 Restricciones de diseño
    3.5 Atributos del sistema de software
    3.6 Información de soporte
4. Apéndices
    4.1 Suposiciones y dependencias
    4.2 Acrónimos y abreviaturas
$\space$
#### 2.1.1.Introducción
El propósito consiste en explicar el propósito del documento que se va a elaborar.

El objetivo tiene que tener nombre. Se debe explicar a grandes rasgos qué va a hacer y qué no va a hacer. Además hay que decidir los objetivos de la empresa en ese proyecto.

El resumen del producto debe tener:
+ Entorno del proyecto, por ejemplo, un diagrama de bloques con las interfaces externas. Por ejemplo, un diagrama de contexto.
+ Funcionalidades del producto. Una buena forma es un listado de casos de uso.
+ Explicar a que tipo de usuarios está enfocado el producto. Por ejemplo, el nivel de educación, la experiencia, el trabajo, etc.
+ Limitaciones por temas de seguridad, de legislación, etc.
$\space$
#### 2.1.2.Apéndices
Las suposiciones y dependencias son asunciones que afectan a los requisitos, de forma que si nuestras teorías cambian, la especificación cambiará.
$\space$
#### 2.1.3.Requisitos específicos
Las interfaces externas es una enumeración detallada de todas las interfaces externas con las que los usuarios interactúan con el sistema. 

Las funciones son los requisitos funcionales (casos de uso).

Los requisitos de rendimiento no son exactamente requisitos no funcionales. Por ejemplo, la carga máxima de usuarios que puede soportar, la velocidad de ciertas funcionalidades, etc. En nuestro caso poner las búsquedas/segundo.

Las restricciones de diseño son el tipo de SO en el que vamos a desplegar el software, el tipo de disco duro que se usará, el impacto medioambiental, etc.

Los atributos del sistema software son los requisitos de accesibilidad, observabilidad (capacidad de observar el rendimiento del sistema), seguridad, etc. Por ejemplo, saber cuántas consultas recibo.

En información de soporte va lo que no cuadra en los apartados anteriores.
$\space$
## 3.Sección 9.2
Explica que tiene que llevar la portada. Una ERS debe ser lo suficientemente detallada para servir como parte de un contrato entre un cliente y un proveedor. Además debe ser lo suficientemente buena para poder realizar las pruebas de aceptación.