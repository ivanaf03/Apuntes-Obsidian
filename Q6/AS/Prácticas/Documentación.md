[[Elixir]]

Ejercicios asociados:
+ [[City office]]

# 1.Docs
Existen tres atributos de módulo que se usan para la documentación:
+ [>] *`@moduledoc`:* describe el módulo, se usa en la primera línea.
+ [>] *`@doc`:* describe una función.
+ [>] *`@typedoc`:* describe un tipo personalizado.

```elixir
defmodule MathOperations do
  @moduledoc """
  Este módulo proporciona funciones para realizar operaciones matemáticas básicas.
  """

  @typedoc """
  Represents an integer number.
  """
  @type number :: integer

  @doc """
  Suma dos números.

  ## Examples

      iex> MathOperations.sum(2, 3)
      5

  """
  def sum(a, b) when is_integer(a) and is_integer(b) do
    a + b
  end

  @doc """
  Resta dos números.

  ## Examples

      iex> MathOperations.subtract(5, 3)
      2

  """
  def subtract(a, b) when is_integer(a) and is_integer(b) do
    a - b
  end
end
```

# 2.Ayuda
Podemos acceder a la documentación utilizando `h` delante de cualquier función de elixir. Se hace en la consola `iex`. 

```elixir
iex()> h String.upcase/1
# def upcase(string, mode \\ :default) 
# 
# Converts all characters in the given string to uppercase according to mode.
# (...)
```