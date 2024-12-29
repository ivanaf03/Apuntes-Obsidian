[[Tema 1-Introducción a .NET]]

## Cómo está formado .NET?
.NET es un framework que incluye un entorno de ejecución, el CRL y librerías. Existen 3 variantes:
+ **.NET framework Redistributable Package:** contiene el CRL y librerías.
+ **.NET framework SDK:** contiene a mayores compiladores, depuradores, etc.
+ **.NET Compact Framework:** contiene el CRL y librerías, pero mucho mas livianas.

## Common Language Runtime
El CLR, además de ejecutar aplicaciones, tiene las siguientes funciones:
+ Recolecta la basura.
+ Aísla unas aplicaciones de otras.
+ Aplica políticas de seguridad.
+ Proporciona servicios de debug.
+ Incluye control de versiones.
+ Desacopla la aplicación del SO.

## Class Library
.NET ofrece una serie de clases e interfaces organizados en namespaces de forma jerárquica. Un ejemplo sería `System.Collections`. 

Los tipos son independientes del lenguaje que se esté usando. Todas las librerías están disponibles para todos los lenguajes. Se pueden extender las librerías, ya que están totalmente orientadas a objetos. Se dividen en 2 subgrupos.

### Base Class Library
Es un pequeño conjunto de librarías que incluye funcionalidades básicas. Por ejemplo, manejo de strings, acceso a bases de datos, colecciones, etc.

### Framework Class Library
Es una colección mucho más grande que incluye la propia BCL y funcionalidades mucho más específicas, como librerías web, librerías de gráficos, etc. Contiene LINQ, ADO.NET, ASP.NET y muchas más.

### Enterprise Library
Es una librería a parte de la Class Library que contiene funcionalidades comunes en aplicaciones empresariales. Por ejemplo, manejo de excepciones, sistemas de caché, seguridad, etc.

## Common Type System
> [!abstract] Definición de Common Type System
> El Common Type System (CTS) es un conjunto de reglas que tienen que seguir las definiciones de datos para que el CLR las acepte. 

Define datos orientados a objetos. La filosofía de .NET es que todo es un objeto, por tanto, todo hereda de `System.Object`. Todos los lenguajes de programación .NET implementan los tipos definidos por el CTS. Aunque no los implementen todos, basta con que implementen un subconjunto conocido como Common Language Specification.

![[CTS.png]]

### Common Language Specification
> [!abstract] Definición de Common Language Specification
> El Common Language Specification (CLS) es el conjunto mínimo de características que todos los lenguajes deben soportar para ajustarse al CLR. 

Esto permite que todos los componentes que sigan esta especificación pueda interactuar entre sí independientemente del lenguaje en que fueran escritos. Solo define los tipos y métodos visibles externamente para que estos sean accesibles desde cualquier lenguaje de programación. Las reglas no afectan al código del assembly en que se definen.

## Assemblies
> [!abstract] Definición de assembly
> Un assembly o ensamblado es la unidad mínima de ejecución, instalación, distribución y versionado de aplicaciones .NET. 

Son ficheros con extensiones `.exe` o `.dll`.

Están formados por código IL y por el manifest, que es la metadata del conjunto de archivos que conforman el assembly. Uno o varios assemblies forman una aplicación .NET.

### Tipos de assemblies
Pueden ser:
+ **Privados:** solo pueden ser usados por una aplicación.
+ **Compartidos:** pueden ser usados por varias aplicaciones. Se instalan en la Global Assembly Cache.

## CLR Hosting y AppDomains
Para ejecutar una aplicación .NET es necesario un Runtime Host. Es un fragmento de código que carga el CLR en un proceso y carga y ejecuta la aplicación en los AppDomains.

### Qué es un AppDomain?
> [!abstract] Definición de AppDomain
> Un AppDomain es un proceso virtual que corre dentro del CLR, que funciona de forma similar a un proceso del SO, pero con la característica de que varios AppDomain pueden correr en el mismo proceso.

Proporcionan aislamiento entre aplicaciones. Esto permite:
+ Detener una sola aplicación sin afectar al resto.
+ Aislar las aplicaciones del código de las otras.
+ Evitar que un fallo afecte al resto.



