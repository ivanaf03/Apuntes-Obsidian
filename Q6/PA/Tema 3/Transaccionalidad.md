[[Tema 3-Capa lógica de negocio con Spring]]

# Transaccionalidad declarativa
Spring permite usar un enfoque declarativo para implementar la transaccionalidad de los métodos de los servicios locales.

+ [<] **Especificaciones:**
+ Mediante ficheros de configuración.
+ Mediante la anotación `@Transactional`.

La anotación `@Transactional` se puede declarar a nivel de clase o de método.
+ [<] **Niveles:**
+ *Clase:* se aplica en todos los métodos públicos.
+ *Método:* sobrescribe la semántica especificada a nivel de clase.

## ¿Qué hace @Transactional?
+ [>] **1.Cuando se invoca a un método anotado:**
+ Si se hace fuera de una transacción, se crea una nueva.
+ Si se hace dentro de una transacción, se une a ella.