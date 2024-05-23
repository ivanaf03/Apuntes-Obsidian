[[Tema 1-Introducción a la arquitectura de software]]
$\space$
## 1.Qué es la arquitectura de software?
La arquitectura de software es la descomposición de software en un conjunto de componentes o módulos más pequeños. Además tiene en cuentas sus relaciones e interacciones.

Definir la arquitectura consiste en realizar la selección de los elementos y ver sus interacciones y restricciones que tienen en el contexto dado, satisfaciendo los requisitos no funcionales. Sirve como base para el diseño e implementación.
$\space$
### 1.1.Diseño vs arquitectura
El diseño se hace siguiendo los requisitos funcionales. Se organiza mediante patrones de diseño. 

La arquitectura deriva de los requisitos no funcionales. Se organiza mediante estilos arquitectónicos. Un mismo diseño puede aparecer en diferentes arquitecturas.
$\space$
### 1.2.Impacto en el software
Para definir la arquitectura hay que tener en cuenta que es la parte donde la toma de decisiones tendrá el mayor impacto en cuanto a coste. Se eligen en esta fase la estructura, las tecnologías y los requisitos no funcionales.

Los diferentes estilos determinan el uso de los elementos y la forma en la que se organizan. Sirven como medio de comunicación para los desarrolladores.
$\space$
## 2.Representación de la arquitectura
La arquitectura se suele representar de forma informal, aunque existen estándares. Por ejemplo, el IEEE 1471.
$\space$
### 2.1.Limitaciones de una representación
Cualquier representación de una arquitectura debe:
+ Indicar en cada componente que papel juega.
+ Mostrar las interacciones entre los componentes.
+ Mantener coherencia entre componentes.
+ Mantener coherencia entre interacciones.
$\space$
### 2.2.Especificación de la arquitectura
Una arquitectura está definida por:
+ Elementos:
	+ Procesos de transformación de datos.
	+ Datos que contienen la información.
	+ Elementos de conexión, como llamadas a procedimientos, mensajes, etc.
+ Forma:
	+ Propiedades de los elementos.
	+ Relaciones.
+ Justificación de la arquitectura:
	+ Motivación de las elecciones.
	+ Claves para evitar desviaciones.
	+ Aspectos funcionales, no funcionales, de negocio, etc.
	
$\space$
### 2.3.Representación de la arquitectura
La arquitectura se representa desde varias vistas:
+ **De datos:** se enfoca en el flujo de datos.
+ **De proceso:** se enfoca en la lógica.
+ **De despliegue:** se enfoca en la distribución física.
$\space$
#### 2.3.1.Modelo C4
El modelo C4 es una forma de representar las vistas de una arquitectura. Se basa en 4 niveles:
+ **Contexto:** relaciona el sistema con otros sistemas.
+ **Contenedores:** muestra la distribución física de los componentes.
+ **Componentes:** muestra las relaciones entre componentes.
+ **Código:** diagramas de componentes y clases UML.