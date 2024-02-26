[[Elixir]]

```elixir
defmodule ResistorColor do
  @doc """
  Return the value of a color band
  """
  @spec code(atom) :: integer()
  def code(:black), do: 0
  def code(:brown), do: 1
  def code(:red), do: 2
  def code(:orange), do: 3
  def code(:yellow), do: 4
  def code(:green), do: 5
  def code(:blue), do: 6
  def code(:violet), do: 7
  def code(:grey), do: 8
  def code(:white), do: 9
end
```