[[Tema 1-Introducción a .NET]]

## Plataforma independiente del lenguaje
A .NET no le importa el lenguaje de programación que se use; permite múltiples lenguajes. Para poder hacerlo convierte el código fuente en Intermediate Language. No es interpretado, hay que compilarlo antes de que pueda ser ejecutado.

Se utiliza el Common Type System (CTS), que son tipos de datos comunes entre todos los lenguajes de .NET. Elegir un lenguaje no condiciona la potencia (teóricamente). Todos los lenguajes soportados tienen la misma capacidad de acceso a recursos y servicios.

## Plataforma de ejecución intermedia
El Common Language Runtime (CLR) es un motor que se encarga de gestionar la ejecución de las aplicaciones .NET. Utiliza compilación Just-In-Time (JIT), que consiste en compilar partes del código justo en el momento que sean necesarias para la ejecución del programa. 

No usa una máquina virtual para ejecutar las aplicaciones. Se genera un fichero ejecutable en formato Portable Executable (PE). Al cambiar el compilador el código debería funcionar en otra plataforma.

## Código gestionado
Las aplicaciones .NET se consideran aplicaciones gestionadas, ya que no se ejecutan directamente sobre el SO, sino en el entorno del CLR. Funciona como un intermediario que controla la carga del código, el recolector de basura, etc.

### Metadatos
Los metadatos se producen en tiempo de compilación. Son descripciones de tipos, propiedades, firmas de métodos y operaciones. Los componentes son autodescriptivos y esto permite interoperabilidad con componentes escritos en otros lenguajes.

## Otras características
Otras características de .NET son:
+ Orientación a objetos.
+ Desarrollo de aplicaciones empresariales.
+ Modelo de programación único para web, hardware, mobile, etc.
+ Tiene peor documentación que Java.