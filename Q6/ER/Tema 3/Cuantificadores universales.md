[[Tema 3-Todo es peligroso]]

## 1.Cuantificadores universales en especificaciones de sistemas software
Cuando asumimos para un caso de un sistema software un cuantificador universal como cierto se suelen producir errores. Hay que buscar siempre excepciones.

Los cuantificadores universales también aparecen en especificaciones formales y causan el mismo tipo de problemas.

### 1.1.Ejemplos
#### 1.1.1.Ejemplo 1: Todos los españoles tienen un DNI único
Es mentira, hace años podía ocurrir que el mismo DNI se asignara a dos personas diferentes.

Hay que tener también en cuenta las posibles anomalías. Por ejemplo, puede haber dos usuarios con el mismo DNI, puede introducirse un DNI incorrecto, los menores de edad no tienen que tener obligatoriamente DNI, etc.

#### 1.1.2.Ejemplos 2: Los ordenadores no se apagan nunca en el CPD
Se pueden apagar por caídas de red, mantenimiento, etc.

#### 1.1.3.Ejemplo 3: El límite de velocidad en carreteras convencionales es 90 km/h
Siempre puede haber conductores saltándose las normas de tráfico.

#### 1.1.4.Ejemplo 4: El sistema debería dejar a un usuario revisar cualquier libro
Podemos pensar que es cualquier libreo del mundo, aunque no exista en el catálogo. Además tampoco se indica se el usuario tiene que haberlo alquilado o no.

Una mejor forma de escribir este requisito es "el sistema debería dejar a un usuario revisar cualquier libro del catálogo de la biblioteca, independientemente de si lo alquilado o no".

### 1.2.Cuándo se pueden usar?
Los cuantificadores universales son válidos en ingeniería de requisitos cuando se utilizan para expresar condiciones que deben ser verdaderas para todos los elementos de un conjunto dado.

## 2.Uso del lenguaje
En Ingeniería de Requisitos se usan dos modos gramaticales:
+ **Modo indicativo:** establece hechos.
+ **Modo optativo:** expresa deseos o intenciones.

### 2.1.Tipos de declaraciones
#### 2.1.1.Dominio
El dominio es el contexto en el que las funcionalidades de un sistema tienen un significado y un efecto. Es una entidad con significado propio, independientemente del sistema que se vaya a construir. Por ejemplo, una biblioteca tiene ciertas reglas y características independientemente del sistema que diseñemos para ella, como que siempre debe haber silencio y el sistema no puede hacer ruido.

El dominio describe el mundo real en modo indicativo. Establece los hechos que son ciertos independientemente del sistema a implementar.

Por ejemplo, para el sistema de billetes del 