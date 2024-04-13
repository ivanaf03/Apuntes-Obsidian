[[Tema 6-Gestión de estado con Redux]]

## 1.Motivación de uso de Redux
En los ejemplo del tema anterior `App` contenía todo el estado de la aplicación y la lógica de modificación del estado ante las interacciones del usuario.

### 1.1.Problemas
En una aplicación real esto puede ocasionar varios problemas:
+ [c] Muchas partes del estado tendrían que ser pasados a componentes hijos desde `App`.
+ [c] Causaría demasiadas renderizaciones en el Virtual DOM.
+ [c] Habría demasiada lógica en `App`.

### 1.2.Otra aproximación
Podemos pensar en solucionar esto distribuyendo el estado entre varios componentes que funcionen como contenedores externos. Reciben parte del estado como propiedades y callbacks para poder manipular el estado ante acciones del usuario.

Sin embargo, esta aproximación no es realista. Se asume que el estado que gestiona un contenedor solo es necesario por los componentes que este contiene.

#### 1.2.1.Ejemplo
En PA-Shop hay varios casos donde no serviría esta aproximación:
+ [c] Los datos del perfil de usuario se usan tanto en el header como en el body. El único componente contenedor de estos es la propia `App`.
+ [c] Los datos del carrito aparecen en el body, pero en el header se usa el número de ítems del carrito. El único componente contenedor vuelve a ser la propia `App`.
+ [c] Los datos de los productos buscados aparecen en el body, pero el body en un componente enorme.
+ [c] Con los datos de los pedidos ocurre lo mismo que en el punto anterior.

## 2.Introducción a Redux
Redux es otra librería de JavaScript que permite solucionar el problema mencionado. Utiliza una arquitectura funcional. Permite gestionar el estado de una aplicación de forma centralizada y modular. Permite recoger la mayor parte del estado y de la lógica de los componentes.

Funciona de forma similar al patrón Provider-Consumer. Los componentes reciben notificaciones cuando cambia el estado. Además permite que el estado que solo se utiliza en un componente sea gestionado por él mismo.

### 2.1.Conceptos principales
El estado de la aplicación se almacena en un objeto llamado `store`. El estado tiene propiedades, que son las ramas del árbol de objetos que mantiene `store`.

#### 2.1.1.Acciones
Cuando queremos modificar el estado se envía un objeto llamado `action` al `store`. Se hace mediante la función `store.dispatch(action)`. La acción contiene la propiedad `type`, que indica el tipo y otras propiedades adicionales.

#### 2.1.2.Reductor
El reductor es el encargado de producir un nuevo estado ante una acción. Se ejecuta al invocar a `store.dispatch(action)`. Devuelve el nuevo estado a partir de la acción y del estado anterior. 

Debe ser una función pura, lo que significa que siempre debe devolver el mismo resultado al pasarle los mismos parámetros. 

El estado es inmutable. El reductor devuelve un nuevo objeto, no modifica el estado anterior. Esto permite reducir el número de renderizaciones en el Virtual DOM.







#### 1.2.3.Notificaciones
Los componentes que lo necesiten reciben una notificación cuando el reductor produce un estado nuevo. Lo hacen mediante `store.subscribe` y leen el estado con `store.getState`. 

Los componentes pueden recibir solo la parte del estado que les interese mediante propiedades o hooks.

