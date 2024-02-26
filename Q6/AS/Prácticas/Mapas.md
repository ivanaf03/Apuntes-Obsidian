[[Elixir]]

Ejercicios asociados:
+ [[High score]]
+ [[Resistor color duo]]
+ [[Resistor color trio]]
+ [[Resistor color]]
+ [[Scrabble score]]
+ [[Binary search tree]]
+ [[Grade school]]
+ [[Kindergarten garden]]
+ [[Tournament]]
+ [[Custom set]]
+ [[Saddle points]]

# 1.Definición
Los mapas son estructuras de datos que guardan pares clave-valor. Las claves pueden ser de cualquier tipo, pero tienen que ser únicas. Los valores pueden ser de cualquier valor y no tienen que ser uno solo. Se declaran con `%{}`.

```elixir
# An empty map
%{}

# A map with the atom key :a associated to the integer value 1
%{a: 1}

# A map with the string key "a" associated to the float value 2.0
%{"a" => 2.0}

# A map with the map key %{} with the list value [1 ,2, 3]
%{%{} => [1, 2, 3]}

# A map with keys of different types
%{:a => 1, "b" => 2}
```

No garantizan el orden del contenido.

# 2.Uso de mapas
## 2.1.Creación de mapas
Podemos crear un mapa a partir de un tipo enumerado, como una lista. Para ello se usa `Map.new/1`.

```elixir
Map.new([{:b, 1}, {:a, 2}])  # %{a: 2, b: 1}
```

## 2.2.Acceso a valores
Podemos acceder a los valores de los mapas de muchas formas.

```elixir
my_map = %{key: "value"}

# con un punto si la clave es un átomo
my_map.key
# => "value"

# con [], una sintaxis proporcionada por Access behaviour
my_map[:key]
# => "value"

# con pattern matching
%{key: x} = my_map
x
# => "value"

# con Map.get/2
Map.get(my_map, :key)
# => "value"
```

## 2.3.Otras funcionalidades
Podemos borrar el valor de un mapa mediante la clave. 

```elixir
Map.delete(%{a: 2, b: 3}, :a)  # %{b: 3}
```

Podemos usar funciones del módulo `Enum`, ya que son un tipo enumerado al igual que las listas.

```elixir
mapa = %{a: 1, b: 2, c: 3}

nuevo_mapa = Enum.map(mapa, fn {k, v} -> {k, v * 2} end)
```

Muchas veces se usan funciones anónimas trabajando con mapas.

```elixir
Map.update(%{a: 1}, :a, 0, &(&1 + 1))
# => %{a: 2}

list = [{"A", 4}, {"B", 3}, {"C", 2}, {"D", 1}]
Enum.sort_by(list, &Kernel.elem(&1, 1))
# => [{"D", 1}, {"C", 2}, {"B", 3}, {"A", 4}]
```