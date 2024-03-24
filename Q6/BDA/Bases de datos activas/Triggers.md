[[Bases de datos activas]]

# 1.Reglas ECA
## 1.1.¿Qué es un trigger?
Los triggers son programación basada en eventos. También se llaman reglas ECA (Evento-Condición-Acción). 

Cuando se produce un evento se dispara el trigger. Las condiciones son opcionales, por defecto se asume que son ciertas. Si la condición es cierta se ejecuta la acción.

## 1.2.Ejemplos
### 1.2.1.Control de salario inválido
Insert: salario<=0, no permite inserción.
Update: salario <=0, no permite actualización.

### 1.2.2.Creación de clave subrogada
Insert: null, generar nuevo id.

### 1.2.3.Log de modificaciones en la tabla de empleados
Insert: null, gravar entrada en el log.
Delete: null, gravar entrada en el log.
Update: null, gravar entrada en el log.

# 2.Estándar SQL
En el estándar un trigger controla una única tabla o vista. Se consideran eventos insertar, actualizar y borrar. Cada trigger responde a un único evento y no valida los datos que ya existían.

Las ventajas del uso de triggers son:
+ [p] Simplifica la codificación de aplicaciones que acceden a la BD.
+ [p] Dan mayor consistencia.

