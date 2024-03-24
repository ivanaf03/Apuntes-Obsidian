[[Tema 5-Desarrolllo basado en componentes React]]

# 1.Mecanismos de optimización
React permite utilizar mecanismos de optimización. Asumen que el estado y las propiedades son inmutables. La idea es que un componente solo se vuelva a renderizar si el valor de las nuevas propiedades que recibe o el estado han variado. Utiliza solo el shallow comparison (igualdad referencial).

