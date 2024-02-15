[[Elixir]]

# Listas en elixir
Las listas son un tipo básico en Elixir. Se denotan entre corchetes. Pueden estar vacías o contener ítems de cualquier tipo.
```elixir
lista_vacia = []
lista_con_elementos = [1, 2, 3, 4, "Hola"]
```

## Notación Head-tail 
Elixir implementa las listas como listas enlazadas. Cada nodo está formado por el primer elemento y la lista restante.
```elixir
# [1] representado en notación [cabeza | cola]
[1 | []]

# [1, 2, 3] representado en notación [cabeza | cola]
[1 | [2 | [3 | []]]]
```

## Algunas operaciones
```elixir
[3, 2, 1] == [3 | lista]  # true

1 in [1, 2, 3, 4]  # true
```