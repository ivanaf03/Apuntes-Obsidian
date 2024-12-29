[[Tema 1-Introducción a .NET]]

## Plataforma independiente del lenguaje
Permite programar en múltiples lenguajes. Para poder hacer esto, transforma el código fuente a Intermediate Language (IL). No es un lenguaje interpretado, hay que compilarlo antes de que pueda ser ejecutado.

El IL utiliza tipos de datos comunes soportados por todos los lenguajes que soporta .NET. Este se conoce como el Common Type System (CTS). Gracias a esto, utilizar un lenguaje u otro no condiciona la potencia. Todos los lenguajes tienen la misma capacidad de acceso a recursos y servicios.

## Plataforma de ejecución intermedia
El Common Language Runtime (CLR) es un motor que se ocupa de gestionar la ejecución de las aplicaciones .NET. Compila el código solo en el momento exacto en que es necesario para ejecutar el programa. Esto se conoce como compilación Just-In-Time (JIT). La utiliza para pasar IL a lenguaje máquina.

No utiliza una máquina virtual para ejecutar las aplicaciones. La compilación genera un fichero ejecutable en formato Portable Executable (PE). Gracias a esto, aunque se cambie el compilador, el código debería funcionar igualmente.

## Código gestionado
Las aplicaciones .NET se consideran aplicaciones gestionadas, ya que no se ejecutan directamente sobre el SO, sino en el entorno del CLR. Este se encarga del recolector de basura, de la carga y verificación del código, etc.

### Metadata
La metadata se produce en tiempo de compilación. Describe tipos, propiedades, firmas de métodos y operaciones. Esto permite que los componentes de .NET sean autodescriptivos y no se necesite información adicional para interactuar entre componentes .NET escritos en otros lenguajes.

## Otras características
Otras características de .NET son:
+ Orientación a objetos.
+ Desarrollo de aplicaciones empresariales.
+ Modelo de programación único para web, hardware, mobile, etc.
+ Tiene peor documentación que Java.