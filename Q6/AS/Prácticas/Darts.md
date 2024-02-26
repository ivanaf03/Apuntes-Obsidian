[[Elixir]]

```elixir
defmodule Darts do
  @type position :: {number, number}

  @doc """
  Calculate the score of a single dart hitting a target
  """
  @spec score(position) :: integer
  def score({x, y}) do
    distance = :math.sqrt(x * x + y * y)
    result(distance)
  end

  defp result(distance) when distance > 10, do: 0
  defp result(distance) when distance > 5, do: 1
  defp result(distance) when distance > 1, do: 5
  defp result(_distance), do: 10
end

```