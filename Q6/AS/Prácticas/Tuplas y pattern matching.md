[[Elixir]]

# Tuplas
Una tupla es un tipo de dato que contiene datos de cualquier tipo, sin darle un nombre concreto a cada elemento. Se denotan entre llaves. Se puede acceder a los elementos de una tuple con `elem`.
```elixir
tupla_vacia={}
tupla_unitaria={1}
tupla_n_elementos={1, :pi, "hola"}

elem(tupla_n_elementos, 2)  # :pi
```

## Representación de información
Las tuplas suelen usarse para representar información. Por ejemplo, numerador y denominador.
```elixir
Float.ratio(0.25)  # {1, 4}
```

# Pattern matching
Permite asignar y desestructurar datos.
```elixir
x = 1  # Se asigna el valor 1 a la variable x
{a, b} = {1, 2}  # Se asigna 1 a la variable a y 2 a la variable b
[head | tail] = [1, 2, 3]  # Se asigna 1 a la variable head y [2, 3] a la variable tail
```

```elixir
defmodule MyModule do
  def example(1), do: "One"
  def example(2), do: "Two"
  def example(_), do: "Other"
end
```

Si no es necesaria una variable se puede sustituir por `_`.
```elixir
{_, denominator} = Float.ratio(0.25)
```


