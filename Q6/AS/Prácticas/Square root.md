[[Elixir]]

```elixir
defmodule SquareRoot do
  @doc """
  Calculate the integer square root of a positive integer
  """
  @spec calculate(radicand :: pos_integer) :: pos_integer
  def calculate(radicand) do
    round(raiz_cuadrada_biseccion(radicand, 0.0001, 0, radicand))
  end

  defp raiz_cuadrada_biseccion(_num, epsilon, a, b) when b - a <= epsilon, do: (a + b) / 2

  defp raiz_cuadrada_biseccion(num, epsilon, a, b) do
    c = (a + b) / 2
    cond do
      c * c == num -> c
      c * c < num -> raiz_cuadrada_biseccion(num, epsilon, c, b)
      true -> raiz_cuadrada_biseccion(num, epsilon, a, c)
    end
  end
end

```