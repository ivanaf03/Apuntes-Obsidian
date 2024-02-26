[[Elixir]]

Ejercicios asociados:
+ [[Kitchen calculator]]
+ [[Binary search]]
+ [[Grains]]
+ [[Matrix]]
+ [[Simple linked list]]

# 1.Definición
Las tuplas son un tipo de dato que se usa para agrupar información. Se definen entre `{}`. Muchas veces en elixir se devuelven valores y estados juntos en una tupla.

```elixir
File.read("hello.txt")  # {:ok, "World"}
File.read("invalid.txt")  # {:error, :enoent}
```

Permiten la lectura de datos a tiempo real.

# 2.Módulo Tuple
El módulo `Tuple` nos da algunas funciones útiles para el manejo de tuplas.

```elixir
Tuple.append({1, 2, 3}, 4)
# => {1, 2, 3, 4} 

Tuple.delete_at({1, 2, 3, 4}, 2)
# => {1, 2, 4} 

Tuple.duplicate(42, 3)
# => {42, 42, 42} 

Tuple.insert_at({1, 2, 4}, 2, 3)
# => {1, 2, 3, 4}

Tuple.product({2, 3, 4})
# => 24 

Tuple.sum({2, 3, 4})
# => 9

Tuple.to_list({1, 2, 3})
# => [1, 2, 3]
```
