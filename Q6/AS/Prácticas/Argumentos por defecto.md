[[Elixir]]

Ejercicios relacionados:
+ [[Guessing game]]
+ [[Two Fer]]

# 1.Funciones con argumentos por defecto
Se pueden declarar valores predeterminados para los argumentos en las funciones con nombre. Si no pone ese parámetro al llamar a una función, esta toma el valor por defecto. Se denotan con `\\`.

```elixir
defmodule Example do
  def greet(name \\ "Mundo") do
    "Hola, #{name}!"
  end
end

IO.puts Example.greet()
# Output: Hola, Mundo!

IO.puts Example.greet("Juan")
# Output: Hola, Juan!
```

Si hay más de un argumento con valores por defecto en una función, los valores por defecto se aplicarán a la función de izquierda a derecha para llenar los argumentos faltantes.
```elixir
defmodule Example do
  def my_function(a \\ 1, b \\ 2, c \\ 3) do
    IO.inspect [a, b, c]
  end
end

Example.my_function()
# Output: [1, 2, 3]

Example.my_function(10)
# Output: [10, 2, 3]

Example.my_function(10, 20)
# Output: [10, 20, 3]
```