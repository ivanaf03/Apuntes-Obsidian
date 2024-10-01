[[Tema 1-Introducción a .NET]]

## Qué es .NET?
Es un framework que incluye un entorno de ejecución, el CLR, y librerías. Se divide en tres variantes:
+ .NET Framework Redistributable Package (CLR + CL)
+ .NET Framework SDK (CLR + CL + compiladores + debuggers)
+ .NET Compact Framework

## Common Language Runtime
El CLR es un entorno de ejecución que puede ser usado por múltiples lenguajes de programación. Se encarga de cargar y ejecutar las aplicaciones .NET traduciendo código IL a lenguaje máquina. 

También tiene un recolector de basura. Además se encarga de aislar las aplicaciones, aplicar políticas de seguridad, dar soporte para control de versiones y proporcionar servicios de debugging.

Funciona como una capa extra que permite separar la aplicación del SO.

## Class Library
El framework incluye una serie de clases e interfaces organizados en namespaces de forma jerárquica. Por ejemplo, `System.Collections`.

Los tipos son independientes del lenguaje de programación que se esté usando. Todos están disponibles para todos los lenguajes. La libraría extensible y orientada a objetos. Se divide en dos partes.

### Blase Class Library
Incluye un pequeño subconjunto de la Class Library. Todas estas clases están disponibles en las diferentes implementaciones del .NET Framework.

### Framework Class Library
Es un superconjunto de las clases de la BCL formado por todas las clases que incluye el framework. Incluye algunas librarías como ADO.NET o ASP.NET.

### Enterprise Library
Es otra librería a parte de la Class Library que agrupa funcionalidades que son comunes en aplicaciones empresariales.

## Common Type System
El CTS es un conjunto de reglas que tienen que seguir las definiciones de los tipos de datos para que el CLR las acepte. Define datos orientados a objetos. 

La filosofía de .NET es que todo es un objeto que hereda de `System.Object`. 

Todos los lenguajes de programación .NET tienen que implementar los tipos definidos por el CTS. No es necesario que los implementen todos, basta con que implementen un subconjunto conocido como CLS. 

![[CTS.png]]

### Common Language Specification
El CLS es el conjunto mínimo de características que todos los lenguajes deben soportar para ajustarse al CLR. Esto permite a todos los componentes interactuar entre sí independientemente del lenguaje en que fueran escritos.

Solo define las reglas con las que se definen los métodos visibles externamente para que puedan ser accesibles a otros lenguajes de programación.

## Assemblies
Un assembly es la unidad mínima de ejecución, distribución, instalación y versionado de aplicaciones .NET. Genera archivos con extensiones `.ddl` o `.exe`.

Está formado por código IL y por el manifiesto, que es un conjunto de archivos que forman el ensamblado. Las aplicaciones .NET se componen de uno o más ensamblados. 

### Tipos de ensamblados
Pueden ser:
+ **Privados:** solo pueden ser usados por una aplicación.
+ **Compartidos:** pueden ser usados por varias aplicaciones. Se instalan en la Global Assembly Cache.

## CLR Hosting y Application Domains
Para ejecutar una aplicación .NET es necesario un Runtime Host. Es un fragmento de código que carga el CLR en un proceso y carga y ejecuta en código en los Application Domains.

Los Application Domains son procesos virtuales del CLR. Se ejecutan dentro de un proceso del SO. Un proceso puede tener varios Application Domains, lo que es más eficiente que tener varios procesos del SO.

Los ensamblados que conforman una aplicación se cargan sobre un Application Domain. 

Los Application Domains permiten aislar las aplicaciones, lo que permite:
+ Detener una sola aplicación sin afectar al resto.
+ Aislar las aplicaciones del código de las otras.
+ Evitar que un fallo afecte al resto.



