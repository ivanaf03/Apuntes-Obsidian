[[Tema 3-Integridad]]
$\space$$\space$
## 1.



# ¿Qué es la integridad?
+ [<] **La información de una BBDD debe ser:**
+ *Completa:* toda la información necesaria debe estar presente. Por ejemplo, no puede haber un empleado sin nombre.
+ *Correcta:* el gestor debe evitar almacenar información errónea, por ejemplo, un sueldo negativo.

## Elementos que garantizan la integridad
+ [<] **Contamos con:**
+ *SGBD transaccional:* considera que la BBDD está en un estado consistente antes de empezar una transacción y cuando termina esta.
+ *Restricciones de integridad:* condiciones que se aplican sobre los datos.
+ *BD Activas:* `triggers` que se ejecutan en el servidor como respuesta a un evento en la BD.

# Fases de diseño
Las condiciones de integridad se aplican en todas las fases de diseño e implementación.
+ [<] **Fases:**
+ *Modelo conceptual:* 
	+ *Diagrama ER:* identificadores, cardinalidad, participación, etc.
	+ *Documentación:* condiciones que no se indican en el ER.
+ *Modelo lógico:* claves primarias, claves foráneas, etc.
+ *Implementación física:* restricciones de integridad y triggers.

## Condiciones de integridad en el modelo físico
+ [<] **Condiciones:**
+ *Valores requeridos:* admisión o no de nulos.
+ *Valores únicos:* valores no duplicados.
+ *Integridad de entidad y clave:* clave primaria y candidatas sin nulos y duplicados.
+ *Integridad referencial:* claves foráneas.
+ *Validez de datos:* valores correctos en atributos, filas y dominios.

