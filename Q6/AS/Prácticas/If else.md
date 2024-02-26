[[Elixir]]

Ejercicios asociados:
+ [[Name badge]]
+ [[Bank account]]

# 1.If y unless
Elixir proporciona las macros `if` y `unless` para casos donde hay una sola condición. `if` devuelve la primera opción si la condición es verdadera y la segunda del `else` si es falsa. `unless` hace exactamente lo contrario.

```elixir
age = 15

if age >= 16 do
  "You are allowed to drink beer in Germany."
else
  "No beer for you!"
end
```

Podemos prescindir del `else`. Devuelve nulo cuando es falsa la condición.

```elixir
age = 15

if age >= 16 do
  "You are allowed to drink beer in Germany."
end
```

También se puede escribir en una sola línea.

```elixir
if age >= 16, do: "You are allowed to drink beer in Germany.", else:  "No beer for you!" 

unless age<16, do: "No beer for you!", else: "You are allowed to drink beer in Germany."
```

# 2.Veracidad de los tipos de datos
Todos los tipos de datos pueden ser evaluados a `truthy` o a `falsy`. Todos son `truthy` excepto `nil` y `false` por defecto.

```elixir
truthy? = fn x -> if x, do: "truthy", else: "falsy" end

IO.puts(truthy?.(true))   # => "truthy"
IO.puts(truthy?.(0))      # => "truthy"
IO.puts(truthy?.([]))     # => "truthy"

IO.puts(truthy?.(false))  # => "falsy"
IO.puts(truthy?.(nil))    # => "falsy"

```
