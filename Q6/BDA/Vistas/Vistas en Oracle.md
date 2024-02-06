[[Vistas]]

## Creación
```sql
create view nombre_vista <lista_atributos>
as <sentencia_select>
with check option;
```

+ Sigue el estándar.
+ Permite `order by` en el `select`.
+ Siempre hace en cascada `with chec option`.
+ Permite restricciones limitadas para las vistas.
+ Permite `replace` en vez de `create`.

## Eliminación
```sql
drop view nombre_vista;
```

+ Borra la vista y marca como inválidas las definidas sobre ella.
+ Permite `cascade constraints`.

## Actualización
```sql
alter view nombre_vista compile;
```

+ Permite volver a marcar una vista como válida.
+ No sirve para modificar la consulta asociada a la vista.

