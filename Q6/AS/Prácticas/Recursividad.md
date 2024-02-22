[[Elixir]]

# Funciones recursivas
Una función recursiva es aquella que se llama a sí misma. Necesita un caso base y un caso recursivo. Generalmente cada uno de estos casos es una función propia.
```elixir
# Caso base
def count([]), do: 0

# Caso recursivo
def count([_head|tail]), do: 1+count(tail)
```