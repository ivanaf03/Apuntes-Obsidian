[[Tema 2-Automatización de procesos]]

## Cómo se implementan los actores?
Para determinar los actores en Bonita hay que crear una organización. A partir de ella, se pueden asociar usuarios reales a las calles del proceso. Para establecer restricciones sobre estos, por ejemplo, establecer que un empleado no pueda aprobar su propio informe de gastos, se recurre a filtros de actor.

En un cao real, los actores se obtienen a partir de un servicio de directorio LDAP (Lightweight Directory Access Protocol). Es un protocolo de autenticación que centraliza la gestión de usuarios y grupos. Permite que los usuarios utilicen sus credenciales para para acceder a diferentes sistemas.

### Alternativa en Bonita Community
En Bonita Community no se puede importar un LDAP. Sin embargo, sí se puede definir una organización en Bonita Studio e importarla a Bonita Portal.

Se define una organización, que puede ser usada en procesos diferentes. Después, se define la jerarquía de departamentos mediante grupos y subgrupos. Finalmente, se indican los roles que tienen los usuarios de la organización. También se puede definir el jefe de cada usuario.

Un usuario puede pertenecer a varios grupos y tener varios roles. En la membresía se define para cada usuario que rol tendrá en cada grupo.

Al guardar la organización en Bonita Studio, se exporta directamente al motor.

## Configuración de actores
En la pool se indican los actores. Uno de ellos debe ser el que puede iniciar el proceso. A cada actor actor abstracto se le pueden asociar grupos, roles y usuarios concretos.

En cada tarea del proceso se puede definir un filtro de actor. Se evalúan en tiempo de ejecución. No tiene por qué ser un usuario o rol concreto, se puede definir con cierta lógica. Por ejemplo, "la tarea C solo la pueden realizar los empleados que no hayan realizado la A o la B" o "la tarea X la tiene que realizar el jefe del empleado que ha iniciado el proceso".