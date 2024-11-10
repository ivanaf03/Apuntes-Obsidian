[[Ferramentas de desenvolvemento]]

POM significa project object model.

El número de versión de maven es un string con una serie de convenciones. Por ejemplo, cuando acaba en SNAPSHOT, es una versión de desarrollo.

Un proyecto maven tiene un padre cuando hay herencia. Ocurre con dependencias, configuraciones, plugins, etc. 

Los proyectos multimódulo empaquetan a pom. 

Como construir un .jar o .war:
1 forma: crear un fatjar, tiene también las dependencias en el jar. 
2 forma: crear un jar ligero, pero para poder ejecutarlo hay que añadir las dependencias.

## Gradle
Problema: no tiene retrocompatibilidad. Gradle utilzia el mismo stack de dependencias de maven. 

