[[Elixir]]

Ejercicios asociados:
+ [[Boutique sugestions]]
+ [[Rectangles]]
+ [[Word search]]
+ [[Book store]]
+ [[Go counting]]
+ [[ETL]]
+ [[Palindrome products]]

# 1.Transformación de enumerables
Para declarar una compresión usamos `for` junto a una operación que actúa sobre los valores del enumerable. 

```elixir
for n <- [0, 1, 2, 3], do: n + 1  # [1, 2, 3, 4]
```

Pueden llevar filtros.

```elixir
for n <- [0, 1, 2, 3], n > 1, do: n + 1  # [3, 4]
```

Puede hacerse en varias líneas.

```elixir
for {atom, number} <- [a: 1, b: 2, c: 3, d: 4], rem(number, 2) == 0 do 
	atom 
end

# => [:b, :d]
```

# 2.Producto cartesiano
Combinando dos compresiones de listas podemos hacer un producto cartesiano.

```elixir
for x <- [0, 1], y <- [0, 1] do
	{x, y}
end

# => [{0, 0}, {0, 1}, {1, 0}, {1, 1}]
```

