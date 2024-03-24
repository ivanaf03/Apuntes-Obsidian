[[Tema 5-Desarrolllo basado en componentes React]]

# 1.Qué es el Virtual DOM?
Los componentes de React no renderizan directamente en el árbol DOM del navegador, sino que en una estructura propia llamada Virtual DOM.

## 1.1.Nomenclatura
Los elementos HTML en realidad son elementos de React. Deben ir en minúsculas. Los creados por el desarrollador tienen que empezar por mayúscula.

Los atributos deben estar en camelCase. Los atributos se nombran de formas especiales a veces. Por ejemplo, `className` en lugar de `class`.

## 1.2.Ventajas
React sigue un modelo de programación muy amigable para el desarrollador. Sus ventajas son:
+ [p] Cada vez que modifica el estado de un componente se vuelve a renderizar.
+ [p] Los componentes que se usan en la renderización también se vuelven a renderizar.
+ [p] La UI siempre está sincronizada con los cambios de estado.

# 2.Renderización de componentes
Cada vez que se renderiza un componente React calcula la diferencia entre el componente antiguo y el nuevo. Mira las diferencias con el DOM del navegador y cambia solo lo necesario.