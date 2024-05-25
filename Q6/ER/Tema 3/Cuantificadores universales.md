[[Tema 3-Todo es peligroso]]
$\space$
## 1.Cuantificadores universales en especificaciones de sistemas software
Cuando asumimos para un caso de un sistema software un cuantificador universal como cierto se suelen producir errores. Hay que buscar siempre excepciones.

Los cuantificadores universales también aparecen en especificaciones formales y causan el mismo tipo de problemas.
$\space$
### 1.1.Ejemplos
Veamos algunos ejemplos.
$\space$
#### 1.1.1.Ejemplo 1: Todos los españoles tienen un DNI único
Es mentira, hace años podía ocurrir que el mismo DNI se asignara a dos personas diferentes.

Hay que tener también en cuenta las posibles anomalías. Por ejemplo, puede haber dos usuarios con el mismo DNI, puede introducirse un DNI incorrecto, los menores de edad no tienen que tener obligatoriamente DNI, etc.
$\space$
#### 1.1.2.Ejemplos 2: Los ordenadores no se apagan nunca en el CPD
Se pueden apagar por caídas de red, mantenimiento, etc.
$\space$
#### 1.1.3.Ejemplo 3: El límite de velocidad en carreteras convencionales es 90 km/h
Siempre puede haber conductores saltándose las normas de tráfico.
$\space$
#### 1.1.4.Ejemplo 4: El sistema debería dejar a un usuario revisar cualquier libro
Podemos pensar que es cualquier libreo del mundo, aunque no exista en el catálogo. Además tampoco se indica se el usuario tiene que haberlo alquilado o no.

Una mejor forma de escribir este requisito es "el sistema debería dejar a un usuario revisar cualquier libro del catálogo de la biblioteca, independientemente de si lo alquilado o no".
$\space$
### 1.2.Cuándo se pueden usar?
Los cuantificadores universales son válidos en ingeniería de requisitos cuando se utilizan para expresar condiciones que deben ser verdaderas para todos los elementos de un conjunto dado.
$\space$
## 2.Uso del lenguaje
En Ingeniería de Requisitos se usan dos modos gramaticales:
+ **Modo indicativo:** establece hechos.
+ **Modo optativo:** expresa deseos o intenciones.
$\space$
### 2.1.Tipos de declaraciones
Se pueden declarar:
+ Dominio
+ Requisitos
$\space$
#### 2.1.1.Dominio
El dominio es el contexto en el que las funcionalidades de un sistema tienen un significado y un efecto. Es una entidad con significado propio, independientemente del sistema que se vaya a construir. Por ejemplo, una biblioteca tiene ciertas reglas y características independientemente del sistema que diseñemos para ella, como que siempre debe haber silencio y el sistema no puede hacer ruido.

El dominio describe el mundo real en modo indicativo. Establece los hechos que son ciertos independientemente del sistema a implementar.

Por ejemplo, para el sistema de las máquinas de billetes de un aeropuerto, hay que tener en cuenta para el dominio que todos los viajeros tienen un DNI, excepto los menores de edad que todavía no lo han obtenido, adultos no registrados o extranjeros no nacionalizados.
$\space$
#### 2.1.2.Requisitos
Un requisito es una afirmación en modo optativo sobre el sistema que queremos construir para mejorar el mundo real. Describe lo que ofrece el sistema y cómo queda el mundo después de que el sistema esté funcionando.

Por ejemplo, el sistema de check-in debe comprobar que el DNI sea correcto y que coincida con los datos del vuelo. Además debe haber algún mecanismo para los viajeros que no tengan DNI.
$\space$
### 2.2.Riesgos y excepciones
Normalmente las afirmaciones universales en indicativo son peligrosas. Si se asumen como ciertas se puede dar que el sistema no sea capaz de manejar todas las posibles entradas. 

Cuando los clientes definen el dominio tienden a usar cuantificadores universales y los ingenieros de requisitos las asumen como ciertas. Normalmente, en algún punto del ciclo de vida del proyecto, se da con las excepciones y se producen fallos.
$\space$
#### 2.2.1.Que hacemos con las afirmaciones en indicativo con cuantificadores universales?
Se debe preguntar al cliente para descubrir posibles excepciones o confirmar si un cuantificador universal es válido. Por ejemplo, si un cliente dice que los usuarios tienen que estar siempre logueados, debemos preguntar si eso es cierto.

En cambio, en modo optativo, si son deseables los cuantificadores universales. Por ejemplo, para todos los usuarios se debe comprobar su DNI. Si no lo tuviesen, el pasaporte...

La clave en modo indicativo es evitar los cuantificadores universales. En cambio, en optativo puede haberlos, siempre y cuando cubramos todas las excepciones del dominio.

