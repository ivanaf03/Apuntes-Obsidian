[[Tema 5-Desarrolllo basado en componentes con React]]

## 1.Gestión de estado
En una aplicación real no existe un único componente que mantiene todo el estado. Cada uno de ellos funcionaría de forma similar a `App` de los ejemplos anteriores. Se renderizan de forma eficiente en el DOM del navegador, pero producen renderizaciones innecesarias en el Virtual DOM.

### 1.1.Mecanismos de optimización
React permite utilizar mecanismos de optimización. Estos asumen que el estado y las propiedades son inmutables. Se provoca que un componente solo se vuelva a renderizar si el valor de las propiedades es diferente al de la última renderización.

Se hace con la igualdad referencial o shallow comparison. Solo compara el nivel más superficial. Esto hace que el software sea muy eficiente.
