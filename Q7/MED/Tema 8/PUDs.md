[[Tema 8-Proceso unificado]]

## Qué son los PUDs?
> [!abstract] Definición de Proceso Unificado de Desarrollo
> El Proceso Unificado de Desarrollo (PUDs) es un marco genérico que organiza actividades necesarias para transformar requisitos en un sistema funcional.

Se adapta a diferentes organizaciones, sistemas y proyectos de todos los tamaños. Proporciona una estructura iterativa e incremental que permite manejar requisitos cambiantes.

### Problemas del desarrollo software
Coordinar varias cadenas de trabajo en proyectos grandes es muy complicado. Los PUDs surgen para coordinar el trabajo, integrar varias facetas del desarrollo y estructurar las actividades y los roles de una forma común para todas las cadenas.

Esto es necesario para:
+ Organizar las actividades.
+ Guiar las tareas individuales y las del equipo como un todo.
+ Especificar los artefactos clave.
+ Proporcionar métricas para controlar el avance del proyecto.

### Características
El PUD se caracteriza por:
+ El sistema está basado en componentes.
+ Se utiliza UML para modelar y documentar.
+ Es iterativo, divide el desarrollo en ciclos o fases bien limitados.

## Pilares de los PUDs
Los aspectos principales del PUD son:
+ Es dirigido por casos de uso.
+ Se centra en la arquitectura.
+ Es iterativo e incremental.

### Proceso dirigido por casos de uso
> [!abstract] Definición de caso de uso
> Un caso de uso es la representación de una interacción significativa entre el usuario y el sistema.

En el proceso unificado, los usuarios no son solo las personas humanas a que se les da servicio.

> [!abstract] Definición de usuario 
> En un PUD, un usuario es cualquier entidad que interactúa con el sistema que se desarrolla, ya sean personas físicas u otros sistemas.

Los casos de uso representan las funcionalidades que hacen que los usuarios obtengan un resultado. Constituyen los requisitos funcionales del sistema. La unión de todos forma el modelo de casos de uso del sistema.

Además de pensar en las funcionalidades, también es importante razonar qué es más importante para el usuario. Son el hilo conductor del desarrollo.

Los casos de uso no especifican simplemente requisitos, también sirven para:
+ Guiar la implementación, diseño y pruebas.
+ Crear modelos de diseño o implementación.
+ Revisar que el sistema cumpla la especificación.
+ Ingeniería de pruebas.

### Proceso centrado en la arquitectura
La arquitectura de un sistema está formada por los aspectos estáticos (la estructura) y los dinámicos (el comportamiento). Surge por las necesidades de los usuarios reflejadas en los CU. Sirve para, a través de vistas, encontrar características críticas y apartar detalles secundarios.

La arquitectura depende de:
+ Plataforma del sistema.
+ Recursos software utilizados.
+ Implementación.
+ Partes legacy.
+ Requisitos no funcionales.

Los casos de uso deben ser compatibles con la arquitectura y avanzar en paralelo. Para definir una arquitectura, los arquitectos software se basan en una pequeña parte de casos de uso del sistema, que deben ser los más críticos.

### Proceso iterativo e incremental
El trabajo se debe dividir en proyectos pequeños y manejables. Las iteraciones deben ser planificadas, ejecutadas y evaluadas. En cada una de ellas se deben aumentar los casos de uso para aumentar la utilidad del producto y resolver los riesgos más críticos.

Las ventajas que esto trae son:
+ Reduce el riesgo.
+ Se cumplen los plazos.
+ Aumenta la productividad.
+ Es un modelo flexible.

