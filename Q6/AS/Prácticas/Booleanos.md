[[Elixir]]

Ejercicios asociados:
+ [[Pacman]]
+ [[Bob]]
+ [[Leap]]

# 1.Variables booleanas
Elixir representa los booleanos como dos valores: `true` y `false`. Pueden aer asignados a variables.

## 1.1.Evaluación de expresiones
Podemos evaluar expresiones utilizando `and/2`, `or/2` o `not/1`.

```elixir
a = true
b = true
true_variable = a and b
IO.puts("True and True: #{true_variable}") # Salida: true

a = true
b = false
false_variable = a and b
IO.puts("True and False: #{false_variable}") # Salida: false

a = false
b = true
true_variable = a or b
IO.puts("False or True: #{true_variable}") # Salida: true

a = false
b = false
false_variable = a or b
IO.puts("False or False: #{false_variable}") # Salida: false

a = false
true_variable = not a
IO.puts("Not False: #{true_variable}") # Salida: true

a = true
false_variable = not a
IO.puts("Not True: #{false_variable}") # Salida: false
```

## 1.2.Funciones booleanas
Se suelen nombrar con un `?` al final. Se usa la misma convención para variables.
```elixir
defmodule BooleanHelpers do
  def is_true?(a?) do
    a? == true
  end
end

IO.puts("#{BooleanHelpers.is_true?(false)}")
```