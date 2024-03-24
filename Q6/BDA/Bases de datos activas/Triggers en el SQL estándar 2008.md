[[Bases de datos activas]]

# 1.Elementos de un trigger
Un trigger está formado por:
+ [>] Nombre de trigger.
+ [>] Nombre de tabla.

## 1.1.Eventos
Son las inserciones, actualizaciones y borrados. Se puede activar un trigger antes o después de un evento. En las vistas se puede utilizar `instead of`.

La granularidad indica cuantas veces se lanza un trigger en un evento. Se indica con `for each {row | statement}`:
+ *Row:* una vez para cada fila afectada.
+ *Statement:* una vez para todo el evento.

## 1.2.Condiciones
Se indican con `when`. Pueden omitirse.

## 1.3.Acciones
Deben ser atómicas. No se recomienda:
+ [c] DML de modificación de datos en triggers `before`.
+ [c] Sentencias de control de transacciones, conexión a BD o DDL.

## 1.4.Tablas de transición
Contienen los valores nuevos y antiguos de los triggers. También se conocen como nombres de correlación. Si se usan se tienen que declarar en la cláusula `referencing`.