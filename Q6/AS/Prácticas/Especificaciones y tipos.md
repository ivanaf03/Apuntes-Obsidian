[[Elixir]]

Ejercicios asociados:
+ [[City office]]

# 1.Especificaciones
Las especificaciones en elixir sirven como documentación, ya que es un lenguaje dinámicamente tipado. Se hacen con `@spec` antes de la definición de la función.

```elixir
@spec longer_than?(String.t(), non_neg_integer()) :: boolean()
def longer_than?(string, length), do: String.length(string) > length
```

## 1.1.Tipos permitido
Las especificaciones permiten:
+ [>] Boolean(), integer(), non_neg_integer(), pos_integer(), float(), lis(), map(), any()
+ [>] Uniones de tipos, por ejemplo, integer() | list(integer()) 
+ [>] Tipos parametrizados, por ejemplo, %{age: integer()} 
+ [>] Tipos de módulo, por ejemplo, String.t()
+ [>] Literales, por ejemplo, :ok
+ [>] char(), charlist(), keyword()
+ [>] Tipos personalizados

## 1.2.Nombrado de argumentos
Se pueden nombrar los argumentos de las funciones en el `@spec`. 

```
@spec to_hex({hue :: integer, saturation :: integer, lightness :: integer}) :: String.t()
```

# 2.Tipos personalizados
Elixir permite definir tipos mediante atributos de módulo:
+ [>] *`@type`:* tipo público.
+ [>] *`@typep`:* tipo privado.
+ [>] *`@opaque`:* tipo público con estructura privada. 

```elixir
defmodule Geometry do
  @moduledoc """
  Este módulo proporciona tipos y funciones para operaciones geométricas.
  """

  @type point :: {number, number}
  @typep triangle :: {point, point, point}
  @opaque rectangle :: {point, point}

  @doc """
  Calcula el área de un triángulo dado sus puntos.

  ## Examples

      iex> Geometry.triangle_area({0, 0}, {4, 0}, {0, 3})
      6.0
  """
  def triangle_area({{x1, y1}, {x2, y2}, {x3, y3}}) do
    abs(x1*(y2-y3) + x2*(y3-y1) + x3*(y1-y2)) / 2.0
  end

  @doc """
  Calcula el área de un rectángulo dado sus puntos opuestos.

  ## Examples

      iex> Geometry.rectangle_area({{0, 0}, {4, 3}})
      12
  """
  def rectangle_area({{x1, y1}, {x2, y2}}) do
    abs(x2 - x1) * abs(y2 - y1)
  end
end

```

# 3.String.t(), binary() y string()
El tipo más correcto para utilizar strings en elixir es `String.t()`, que son binarios codificados en UTF-8. Es lo mismo que `binary()`. En cambio `string()` es un tipo de Erlang. Realmente es una lista de caracteres, pero en elixir es mejor usar `charlist()`.