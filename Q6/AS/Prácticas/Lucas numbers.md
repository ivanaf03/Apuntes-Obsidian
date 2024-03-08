[[Elixir]]

```elixir
defmodule LucasNumbers do
  @moduledoc """
  Lucas numbers are an infinite sequence of numbers which build progressively
  which hold a strong correlation to the golden ratio (φ or ϕ)

  E.g.: 2, 1, 3, 4, 7, 11, 18, 29, ...
  """

  def generate(count) when not is_number(count) or count <= 0 do
    raise ArgumentError, message: "count must be specified as an integer >= 1"
  end

  def generate(count) when count < 1, do: []
  def generate(count) when count == 1, do: [2]
  def generate(count) when count == 2, do: [2, 1]
  def generate(count) do
    Stream.unfold({2, 1}, fn {a, b} -> {a, {b, a+b}} end)
    |> Enum.take(count)
  end
end
```