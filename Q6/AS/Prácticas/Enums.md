[[Elixir]]

Ejercicios asociados:
+ [[Boutique inventory]]
+ [[Zebra puzzle]]
+ [[Anagram]]
+ [[Hamming]]
+ [[Raindrops]]
+ [[Sum of multiples]]
+ [[Pythagorean triplet]]
+ [[Transpose]]
+ [[Connect]]
+ [[Minesweeper]]

# 1.Módulo Enum
El módulo `Enum` contiene una serie de algoritmos que permiten trabajar con tipos enumerados. Permite, entre muchas otras cosas:
+ [>] Ordenar
+ [>] Filtrar
+ [>] Agrupar
+ [>] Contar
+ [>] Buscar
+ [>] Buscar valores mínimos y máximos

 $\space$
 Los tipos enumerados son aquellos que implementan el protocolo `Enumerable`. Los más comunes son las listas y los mapas. Las funciones más comunes son `map/2` y `reduce/3`.

```elixir
numbers = [1, 2, 3, 4, 5]

Enum.map(numbers, fn(x) -> x * 2 end)  # [2, 4, 6, 8, 10]

Enum.reduce(numbers, 0, fn(x, acc) -> x + acc end)  # 15
```

# 1.1.Mapas
Las funciones de `Enum` convierten los mapas en listas de tuplas. Para volver a transformarlos en mapas podemos usar `into/2`.

Además existe `into/3`, que acepta una función que se aplica al transformarlo.

```elixir
list_of_tuples = [{:a, 1}, {:b, 2}, {:c, 3}]
map_result = Enum.into(list_of_tuples, %{})
IO.inspect(map_result)  # Salida: %{a: 1, b: 2, c: 3}

list_of_tuples = [{:a, 1}, {:b, 2}, {:c, 3}]
map_result = Enum.into(list_of_tuples, %{}, fn {key, value} -> {String.upcase(key), value * 2} end)
IO.inspect(map_result)  # Salida: %{"A" => 2, "B" => 4, "C" => 6}
```

Podemos usar `Map.new/2` para hacer un mapeado directamente en vez de `Enum.into/3`.

```elixir
Map.new([:a, :b], fn x -> {x, x} end)  # %{a: :a, b: :b}
```

