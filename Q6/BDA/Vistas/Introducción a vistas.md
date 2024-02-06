[[Vistas]]

## Vistas en arquitectura ANSI/SPARK
En el esquema conceptual se definen las tablas y las reglas de integridad. En el esquema físico se definen los ficheros donde se guarda la información. En el esquema externo se ofrece a cada usuario la visión que necesita mediante las vistas.

Ayudan a conseguir independencia lógica, es decir, podemos hacer cambios en el esquema conceptual sin que el usuario lo note en las vistas.

## Vistas para SQL 
Una vista es una tabla virtual porque no almacena datos, simplemente los expone. Estos datos se obtienen como consultas de otras tablas o vistas.

Una tabla almacena su información en el catálogo y los almacena. Pueden ser:
+ **Permanentes:** Conservan los datos hasta que se borran.
+ **Temporales:** Cada usuario puede ver sus filas hasta que se desconectan. Puede configurarse para que desaparezcan después de cada transacción.

Una vista tiene:
+ Nombre
+ Lista de atributos (columnas)
+ Definición (sentencia `SELECT`)

Las vistas no optimizan las consultas. Una vista materializada es una vista que mantiene una caché para almacenar los datos.