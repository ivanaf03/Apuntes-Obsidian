[[Elixir]]

```elixir
defmodule ResistorColorTrio do
  @doc """
  Calculate the resistance value in ohms from resistor colors
  """
  @spec label(colors :: [atom]) :: {number, :ohms | :kiloohms | :megaohms | :gigaohms}
  def label([a, b, c|_]) do

    zeros = String.duplicate("0", String.to_integer(take_num(c)))
    value = String.to_integer(take_num(a) <> take_num(b)<>zeros)

    cond do
      value == 0 -> {value, :ohms}
      rem(value, 1000000000) == 0 -> {div(value, 1000000000), :gigaohms}
      rem(value, 1000000) == 0 -> {div(value, 1000000), :megaohms}
      rem(value, 1000) == 0 -> {div(value, 1000), :kiloohms}
      true -> {value, :ohms}
    end
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