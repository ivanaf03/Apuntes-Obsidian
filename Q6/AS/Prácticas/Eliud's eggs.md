[[Elixir]]

```elixir
defmodule EliudsEggs do
  @doc """
  Given the number, count the number of eggs.
  """
  @spec egg_count(number :: integer()) :: non_neg_integer()
  def egg_count(number) do
    list=to_binary(number)
    Enum.count(list, &(&1 == 1))
  end

  defp to_binary(0) do
    []
  end

  defp to_binary(number) do
    [rem(number, 2) | to_binary(div(number, 2))]
  end
end

```