[[Bases de datos activas]]

# 1.Bases de datos activas y pasivas
Las bases de datos pasivas son simples almacenes de datos. Hoy en día apenas existen. 

## 1.1.Bases de datos activas
Las bases de datos activas realizan controles con restricciones y reaccionan ante eventos como cambios en los datos.

Las ventajas de esto son:
+ [p] *Control de restricciones:* validaciones de DNI, salario, etc. o reglas como que un empleado no gane más que su jefe.
+ [p] *Actualización de datos:* generación de claves primarias, campos autoactualizados, etc.
+ [p] *Acciones externas a la base de datos:* alertas, como un stock mínimo de un producto.

$\space$
Estas actividades se suelen implementar con triggers.

# 2.Actividades sin triggers
