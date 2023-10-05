[[Tema 3-Diseño e implementación de la capa modelo]]

### Implementación mediante los DAO
La implementación de los servicios corresponde  a la capa lógica de negocio. Debemos tener en cuenta:
+ Gestión de transacciones
+ Obtención de referencias a DataSource
+ Obtención de referencias a DAOs
+ Obtención de referencias al propio servicio desde el cliente

##### Gestión de transacciones
+ Para casos de uso que solo ejecutan una operación de lectura contra la BD: auto-commit y nivel de aislamiento por defecto
+ Resto de casos: 
	1. Validar datos de entrada
	2. Empezar transacción
	3. Comprobar que es posible ejecutarlo
	4. Si no es posible: checked+commit
	5. Implementar la capa lógica de negocio
	6. Si hay un error grave: rollback
	7. En cualquier otro caso: commit
