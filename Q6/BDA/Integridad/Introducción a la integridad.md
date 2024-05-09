[[Tema 3-Integridad]]
$\space$$\space$
## 1.Qué es la integridad?
La integridad es la propiedad que garantiza que la información de una base de datos sea:
+ **Completa:** toda la información necesaria debe estar presente. Por ejemplo, no puede haber un empleado sin nombre.
+ **Correcta:** el gestor debe evitar que la base de datos contenga información errónea. Por ejemplo, no puede almacenarse un sueldo negativo.
$\space$$\space$
### 1.1.Elementos que garantizan la integridad
Para garantizar la integridad contamos con:
+ **SGBD transaccional:** permite que la base de datos pase de un estado consistente a otro desde el inicio al fin de una transacción. Durante la transacción esto no tiene por que cumplirse.
+ **Restricciones de integridad:** son condiciones que se aplican sobre los datos y que el gestor verifica.
+ **BD Activas con triggers:**  es código que se ejecuta como respuesta a un evento producido en la base de datos. Se suelen usar cuando no se puede garantizar la integridad mediante los dos casos anteriores. 
$\space$$\space$
## 2.Integridad en las fases de diseño
La integridad aparece en todas las fases:
+ **Modelo conceptual:** 
	+ En el diagrama ER se utilizan identificadores, cardinalidades, participaciones, etc.
	+ El la documentación, por ejemplo, en los DD, se ponen las condiciones que no se pueden expresar en el ER.
+ **Modelo lógico:** se ponen las claves primarias y foráneas.
+ **Implementación:** se indican las restricciones de integridad y los triggers que sean necesarios.
$\space$$\space$
### 2.1.Condiciones de integridad en la implementación
Se deben tener en cuenta:
+ **Valores requeridos:** se el valor permite o no nulos.
+ **Valores únicos:** valores no duplicados.
+ **Integridad de entidad y clave:** clave primaria y claves candidatas sin nulos ni duplicados.
+ **Integridad referencial:** claves foráneas.
+ **Validez de datos:** valores correctos en atributos, filas o dominios. 

