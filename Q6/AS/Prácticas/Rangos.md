[[Elixir]]

Ejercicios asociados:
+ [[Chessboard]]
+ [[Nth prime]]
+ [[Pangram]]
+ [[Rotational cipher]]
+ [[Sum of multiples]]
+ [[Grains]]
+ [[ISBN verifier]]
+ [[Difference of squares]]
+ [[Palindrome products]]
+ [[Rail fence cipher]]

# 1.Rangos de enteros
Un rango es una secuencia de uno o más enteros consecutivos. Se crean con `int..int`. 

Pueden ser ascendentes o descendentes. Incluyen el primer y el último valor. Implementan el protocolo `Enumerable`.

```elixir
# Crear un rango de números enteros
range = 1..5

# Iterar sobre el rango e imprimir cada valor
Enum.each(range, fn(x) -> IO.puts(x) end)

# Verificar si un valor está dentro del rango
IO.puts(3 in range) # Output: true
IO.puts(6 in range) # Output: false

# Obtener la lista de valores del rango
list = Enum.to_list(range)
IO.inspect(list) # Output: [1, 2, 3, 4, 5]
```