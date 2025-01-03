[[Tema 3-Implementación de persistencia con ADO.NET Entity Framework]]

## Estados de los datos en una instancia
![[estados_ef.png]]

Los datos de una instancia pueden pasar por los estados:
+ **Detached:** no vinculados al contexto.
+ **Unchanged:** vinculada al contexto y sin cambios, con valores de clave finales.
+ **Added:** vinculados al contexto con valores de clave temporales.
+ **Modified:** con cambios en las propiedades.
+ **Deleted:** eliminados.

### Cambios entre estados
Para pasar de un estado a otro se utilizan los métodos:
+ **AddObject:** añade una instancia con el estado Added.
+ **Attach:** vincula una entidad a Unchanged.
+ **DeleteObject:** marca una entidad como Deleted.
+ **AcceptAllChanges:** marca todas las entidades como Unchanged.
+ **Detach:** elimina una entidad del contexto.
+ **ChangeState y ChangeObjectState:** modifican el estado de una entidad a otro.
+ **ApplyCurrentValues y ApplyOriginalValues:** cambian el estado a Modified.
