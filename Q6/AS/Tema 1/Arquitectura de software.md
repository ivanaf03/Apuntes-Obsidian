[[Tema 1-Introducción a la arquitectura de software]]

## ¿Qué es la arquitectura de software?
Es la descomposición de un software en componentes o módulos y las interacciones entre ellos. Definir la arquitectura consiste en realizar la selección de elementos, como interactúan entre ellos y las restricciones que proporciona el contexto que satisface los requisitos no funcionales. Sirve como base para el diseño e implementación.

Para definirla se toman decisiones en función al impacto que tendrán en cuanto al coste de los cambios.

Los estilos de arquitectura determinan el uso de elementos y como se organizan. Sirven para comunicar a los desarrolladores, al igual que los patrones de diseño software.

## Diseño frente a arquitectura
El diseño:
+ Viene de los requisitos funcionales.
+ Se organiza mediante patrones de diseño.
+ Pode utilizarse en diferentes arquitecturas.

La arquitectura:
+ Viene de los requisitos no funcionales.
+ Se organiza mediante estilos de arquitectura.

## Representación
Se suele representar la arquitectura de forma no funcional y heterogénea. El estándar, aunque no se suele seguir, es el IEEE 1471.

Las representaciones deben:
+ Indicar qué es cada componente y qué hace.
+ Mostrar las interacciones entre los componentes y la finalidad.
+ Mantener coherencia entre componentes.
+ Mantener coherencia entre iteraciones.

Se representa mediante diagramas. Antes se especificaban:
+ Elementos de la arquitectura
	+ Procesos: elementos que hacen cosas.
	+ Datos: elementos que contienen información.
	+ Elementos de conexión: llamadas, mensajes, contenidos, etc.
+ Forma de la arquitectura
	+ Propiedades: restricciones sobre los elementos.
	+ Relaciones: restricciones sobre las interacciones.
+ Justificación de la arquitectura
	+ Motivación de las elecciones.
	+ Evita derivaciones y errores.
	+ Incluye aspectos económicos, de negocio, etc.

Se representa como una combinación de vistas:
+ De datos o estática: flujo de datos.
+ De proceso o dinámica: flujo de lógica.
+ De despliegue o física: distribución física.

## Modelo C4
Se representa la arquitectura como 4 vistas:
+ Contexto: relación do sistema con otros.
+ Contenedor: distribución física de componentes.
+ Componente: relaciones entre componentes.
+ Código: diagramas UML.