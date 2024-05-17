[[Tema 5-Bases de datos activas]]
$\space$
## 1.Qué es un trigger?
Un trigger es un método que permite programar basándose en eventos en base de datos. También se llaman reglas ECA (Event-Condition-Action).

Cuando se produce un evento se dispara el trigger. Las condiciones son opcionales, pero por defecto se asume que se cumplen. Si la condición es cierta, se ejecuta la acción.
$\space$
### 1.1.Ejemplos de uso
Se pueden usar para:
+ Control de salario
+ Validación de NIF
+ Limite de empleados para un departamento
+ Enviar un correo cuando el stock pasa del límite.
$\space$
### 1.2.Triggers en el estándar
En el estándar un trigger controla una única tabla o vista. Se consideran eventos insertar, actualizar y borrar. Cada trigger responde a un único evento y no valida los datos que ya existían.
$\space$
#### 1.2.1.Ventajas
Las ventajas del uso de triggers son:
+ [p] Simplifica la codificación de aplicaciones que acceden a la BD.
+ [p] Dan mayor consistencia.
$\space$
## 2.Reglas ECA
Se suelen plantear reglas ECA para hacer los triggers. Por ejemplo:
+ **Control de salario inválido:** E: insert/update, C: salario <=0, A: no permitir
+ **Creación de clave subrogada:** E: insert, C: null, A: generar nuevo ID
+ **Log de modificaciones en la tabla de empleados:** E: insert/delete/update, C: null, A: grabar en log


