[[Tema 3-Capa lógica de negocio con Spring]]

# Servicios locales
Los servicios locales usan los DAOs y el servicio interno `PermissionChecker`. La implementación de cada servicio debe poder obtener una instancia de cada DAO y el servicio interno sin conocer las clases de implementación.

Se podría definir una factoría para cada DAO, pero en una situación real habría demasiadas factorías. Los framework utilizan el principio de inyección de dependencias.

Consiste en tener un contenedor de objetos que crea los objetos y les inyecta las referencias a los objetos de los que dependen.

+ [<] **Se usa:**
+ Ficheros
+ Anotaciones

## Inyección de dependencias mediante anotaciones
