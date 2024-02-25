[[Elixir]]

```elixir
defmodule CollatzConjecture do
  @doc """
  calc/1 takes a positive integer and returns the number of steps required to get the
  number to 1 when following the rules:
    - if number is odd, multiply by 3 and add 1
    - if number is even, divide by 2
  """
  @spec calc(input :: pos_integer()) :: non_neg_integer()
  def calc(input) when is_integer(input) and input > 0 do
    calc_in(input, 0)
  end

  defp calc_in(1, acc), do: acc
  defp calc_in(n, acc) when rem(n, 2) == 0 do
    calc_in(div(n, 2), acc + 1)
  end
  defp calc_in(n, acc) do
    calc_in(3 * n + 1, acc + 1)
  end
end
```