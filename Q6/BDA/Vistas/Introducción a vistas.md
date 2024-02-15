[[Vistas]]

# Vistas en arquitectura ANSI/SPARK
+ [<] **Arquitectura:**
+ *Esquema conceptual:* define las tablas y las reglas de integridad. 
+ *Esquema físico:* define los ficheros donde se guarda la información.
+ *Esquema externo:* ofrece a cada usuario la visión que necesita mediante las vistas.

Las vistas permiten definir varios esquemas externos. Ofrecen a cada usuario una visión adecuada de la BBDD. Ayudan a conseguir independencia lógica, es decir, podemos hacer cambios en el esquema conceptual sin que el usuario lo note en las vistas.

# Vistas para SQL y SGBD relacionales
Una vista es una tabla virtual. No almacena datos, simplemente los expone. Estos datos se obtienen como consultas de otras tablas o vistas.

## Tablas
Una tabla almacena su definición en el catálogo y los datos los almacena en el espacio de datos.
+ [<] **Tipos:**
+ *Permanentes:* Conservan los datos hasta que se borran.
+ *Temporales:* Cada usuario puede ver sus filas hasta que se desconectan. Puede configurarse para que desaparezcan después de cada transacción.

## Vistas
Una vista solo almacena la definición en el catálogo. No almacena datos.
+ [<] **Contienen:**
+ Nombre
+ Lista de atributos (columnas)
+ Definición (sentencia `SELECT`)

Pero tienen su parte mala.
+ [c] **Contras:**
+ Las vistas no optimizan las consultas. 

### Vista materializada
Una vista materializada es una vista que mantiene una caché para almacenar los datos. Sí almacena datos en el espacio de datos.