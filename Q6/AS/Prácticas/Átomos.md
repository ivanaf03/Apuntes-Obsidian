[[Elixir]]

Ejercicios asociados:
+ [[Log level]]
+ [[Resistor color duo]]
+ [[Resistor color trio]]
+ [[Resistor color]]
+ [[Space age]]
+ [[Triangle]]
+ [[Grains]]
+ [[Perfect numbers]]
+ [[Meetup]]
+ [[Simple linked list]]

# 1.¿Qué son los átomos?
Los átomos son variables que actúan como constantes. Proporcionan un valor que suele usarse para compararse con otros. Se define con el operador `:` y un nombre. Internamente son enteros que se almacenan en una tabla.

```elixir
:atomo
```

Muchas funciones de elixir devuelven átomos.

```elixir
Enum.fetch([1], 0)  # {:ok, 1}
```

