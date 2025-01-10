[[Tema 1-Entornos integrados de desarrollo]]

## Vista Java projects
Esta vista está diseñada para manejar proyectos Java, junto a sus dependencias. Por defecto, se sitúa justo debajo del explorador de archivos. Puede alternarse entre dos vistas:
+ **Vista plana:** agrupa los paquetes vacíos como si fueran el mismo directorio.
+ **Vista jerárquica:** mantiene toda la jerarquía en forma de escalera.

## Editor de Java
El editor de Java permite:
+ Navegar entre los miembros de un archivo mediante la vista de esquema.
+ Buscar símbolos tanto en todo el workspace como en el archivo actual.
+ Inspeccionar definiciones.
+ Mantener el seguimiento de las implementaciones y jerarquías.

### Spring Boot Tools
Es una extensión que facilita la navegación y el autocompletado de código en proyectos de Spring Boot. Mediante el atajo control+T permite buscar:
+ **RequestMappings:** con @/.
+ **Beans:** con @+.
+ **Funciones:** con @>.
+ **Anotaciones:** con @.

### Cómo ahorrar tiempo programando en Java
Las extensiones permiten el uso de herramientas que nos ahorran un montón de tiempo:
+ **IntelliSense:** autocompletado de código.
+ **Code snippets:** proporciona estructuras de código ya hecho.
+ **Code actions:** organización de imports, source actions para los constructores, getters, setters, etc.
+ **Quick fixes:** detecta errores comunes y los soluciona automáticamente.

![[code snippets 1.png]]

![[code snippets 2.png]]

Funcionan de forma similar los postfix snippets. Siguen la siguiente estructura: `(var).postfix`.

![[postfix.png]]

## Refactorización en Java
El objetivo de la refactorización es realizar cambios en todo el sistema sin que el funcionamiento de este se vea afectado. VSCode proporciona varias acciones de refactorización:
+ Asignar expresiones a variables locales.
+ Cambiar clases internas anónimas por clases miembro.
+ Convertir lambdas en clases anónimas.
+ Convertir clases anónimas en lambdas.
+ Convertir bucles `for` en bucles `for-each`.
+ Generar imports estáticos.

### Extracciones
Para mejorar la estructura y la mantenibilidad proporciona:
+ Substituir por una constante.
+ Extraer a una variable local.
+ Extraer a una variable de clase.
+ Extraer a un método.

### Otros cambios
VSCode también permite:
+ Cambiar una constante por su valor.
+ Cambiar una variable por su valor.
+ Cambiar las llamadas de un método por su contenido.
+ Invertir las condiciones en una expresiones booleana.
+ Invertir una variable booleana.
+ Mover elementos.
+ Renombrar todas las referencias con F2.

## Source actions
Las source actions permiten automatizar cosas muy comunes en la POO. Estas son:
+ Generación de constructores, getters, setters, hashCode, equals y toString.
+ Agregación de final donde sea posible.
+ Organización de imports.
+ Generación de métodos e interfaces.