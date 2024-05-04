[[Tema 1-Introducción a la arquitectura de software]]

## 1.Qué es la arquitectura de software?
La arquitectura de software es la descomposición de este en un conjunto de componentes o módulos más pequeños y de sus interacciones. Definir la arquitectura consiste en seleccionar adecuadamente los elementos, sus interacciones y sus restricciones en el contexto dado por los requisitos no funcionales. Es la base del diseño e implementación.

Para definirla se toman decisiones en función al impacto que tendrán en cuanto al coste de los cambios.

Los estilos de arquitectura determinan el uso de los elementos y su organización. Sirven para mejorar el trabajo colaborativo entre los desarrolladores, al igual que los patrones de diseño software.

### 1.1.Diseño vs arquitectura
El diseño se hace siguiendo las requisitos funcionales. Se realiza mediante patrones de diseño y un mismo diseño se puede utilizar en diferentes arquitecturas.

La arquitectura deriva de los requisitos no funcionales. Se realiza mediante estilos arquitectónicos.

## 2.Representación de la arquitectura
La arquitectura se suele presentar de forma informal y heterogénea. Se pueden utilizar muchas herramientas y métodos para representarla de forma similar. Existe un estándar, el IEEE 1471, pero no se suele seguir.

### 2.1.Limitaciones
Las representaciones para ser correctas deben:
+ Indicar que es cada componente y que rol toman en la arquitectura.
+ Mostrar las interacciones entre los componentes y su finalidad.
+ Mantener coherencia entre componentes similares.
+ Mantener coherencia entre interacciones similares.

### 2.2.Especificación de la arquitectura
#### 2.2.1.Elementos de la arquitectura
En la especificación se deben indicar los elementos que forman la arquitectura. Estos son:
+ **Procesos:** métodos que transforman datos.
+ **Datos:** elementos que contienen la información.
+ **Elementos de conexión:** llamadas a procedimientos, mensajes, etc.

#### 2.2.2.Forma de la arquitectura
En la especificación se debe indicar la forma de la arquitectura. Esta se define por:
+ **Propiedades:** restricciones que tienen los elementos.
+ **Relaciones:** restricciones que tienen las interacciones.

#### 2.2.3.Justificación de la arquitectura
En la especificación se debe justificar por qué se hace cada cosa. Sirve para evitar posibles desvíos en la lógica del software o fallos futuros. Se incluyen requisitos funcionales, no funcionales, de negocio, etc.


### 2.3.Representación de la arquitectura
La arquitectura se representa normalmente mediante una serie de vistas:
+ **De datos:** se enfoca en el flujo de los datos.
+ **De proceso:** se enfoca en la lógica.
+ **De despliegue:** se enfoca en la distribución física.

#### 2.3.1.Modelo C4
Un modelo que se suele utilizar para representar las vistas de la arquitectura es el C4. Está formado por 4 niveles de vistas:
+ **Contexto:** relaciona el sistema con otros sistemas.
+ **Contenedores:** muestra la distribución física de los componentes.
+ **Componentes:** muestra las relaciones entre los componentes.
+ **Código:** son habitualmente los diagramas de clases UML más detallados sobre el código.