[[Tema 6-Gestión de estado con Redux]]

## 1.Motivación de uso de Redux
En el tema anterior, en el ejemplo el componente `App` contenía todo el estado de la aplicación y la lógica de modificación del estado ante las acciones del usuario. 

### 1.1.Contras
En un caso real esto no sería viable por:
+ [c] Parte del estado tendría que pasarse de `App` a los componentes hijos y así de forma recursiva.
+ [c] Causaría demasiadas renderizaciones en el Virtual DOM.
+ [c] `App` contendría demasiada lógica.

### 1.2.Otra aproximación
Podríamos solucionarlo distribuyendo el estado entre algunos componentes contenedores. Los contenedores delegarían en otros componentes de presentación contenidos en ellos. Estos reciben parte del estado como propiedades y callbacks para manipular el estado.

Esta aproximación no sirve en general porque se asume que el estado que gestiona un contenedor solo necesita ser visto por los componentes de presentación que contiene.

#### 1.2.1.Ejemplo de fallo: PA Shop
En PA-Shop hay varios casos donde esta aproximación no serviría:
+ [c] Los datos del perfil del usuario se usan en el header y en el body. El único componente padre que los contiene es la propia `App`.
+ [c] Los datos del carrito aparecen en el header (número de ítems) y en el body en varios casos.
+ [c] etc

## 2.Introducción a Redux
Redux es una librería que utiliza una arquitectura funcional. Permite gestionar el estado de forma centralizada y modular. Permite sacar la mayor parte del estado y la lógica de modificación de los componentes.

Funciona de forma similar al patrón observador. Los componentes reciben notificaciones cuando cambia el estado. El estado que solo sea relevante por un componente puede ser almacenado y gestionado por el propio componente.

### 2.1.Conceptos principales
El estado de la aplicación se almacena en el objeto `store`. Contiene el estado, que tiene propiedades.

#### 2.1.1.Acciones
Cada vez que un componente quiere modificar el estado se envía un objeto acción a `store` con `store.dispatch(action)`. La acción debe contener la propiedad `type` para indicar su tipo y puede contener propiedades.

```javascript
type: 'ADD-TODO' //tipo
text: 'Learn Redux' //propiedad
```

#### 1.2.2.Reductor
El reductor es una función encargada de producir un nuevo tipo de estado ante una acción. Se ejecuta al invocar a `store.dispatch(action)`. Devuelve el estado anterior y el nuevo. 

Debe ser una función pura, lo que significa que siempre debe devolver el mismo resultado al pasarle los mismos parámetros. 

El estado debe ser inmutable. El reductor no modifica el estado anterior, sino que devuelve un nuevo objeto. 

#### 1.2.3.Notificaciones
Los componentes que lo necesiten reciben una notificación cuando el reductor produce un estado nuevo. Lo hacen mediante `store.subscribe` y leen el estado con `store.getState`. 

Los componentes pueden recibir solo la parte del estado que les interese mediante propiedades o hooks.

