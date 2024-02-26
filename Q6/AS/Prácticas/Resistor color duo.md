[[Elixir]]

```elixir
defmodule ResistorColorDuo do
  @doc """
  Calculate a resistance value from two colors
  """
  @spec value(colors :: [atom]) :: integer
  def value([a, b | _]) do
    String.to_integer(take_num(a) <> take_num(b))
  end

   defp take_num(color) do
    case color do
      :black -> "0"
      :brown -> "1"
      :red -> "2"
      :orange -> "3"
      :yellow -> "4"
      :green -> "5"
      :blue -> "6"
      :violet -> "7"
      :grey -> "8"
      :white -> "9"
    end
  end
end

```