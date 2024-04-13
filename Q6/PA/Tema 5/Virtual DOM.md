[[Tema 5-Desarrolllo basado en componentes con React]]

## 1.Qué es el Virtual DOM?
Los componentes de React no renderizan directamente en el DOM del navegador, sino en una estructura llamada Virtual DOM. Contiene el árbol de elementos renderizados por los componentes.

Los elementos HTML de los JSX corresponden con los elementos HTML del mismo nombre. Los nombres de los componentes creados por el desarrollador tienen que empezar por mayúscula, por ejemplo, `Todo`. Los atributos van en camelCase. Existen algunas diferencias, como por ejemplo el uso de `classsName` en lugar de `class` de HTML.

### 1.1.Ventajas
El uso del Virtual DOM permite:
+ [p] Evitar realizar actualizaciones completas del DOM.
+ [p] Mantener siempre la UI sincronizada con el desarrollo.

### 1.2.Funcionamiento
La forma de trabajar del Virtual DOM es muy simple. Cada vez que se renderiza un componente, React calcula la diferencia entre el resultado anterior y el nuevo. Después aplica las diferencias en el DOM del navegador.