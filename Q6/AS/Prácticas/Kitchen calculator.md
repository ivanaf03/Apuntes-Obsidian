[[Elixir]]

```elixir
defmodule KitchenCalculator do
  def get_volume(volume_pair) do
    {_, value} = volume_pair
    value
  end

  def to_milliliter({:cup, value}), do: {:milliliter, value * 240}
  def to_milliliter({:fluid_ounce, value}), do: {:milliliter, value * 30}
  def to_milliliter({:teaspoon, value}), do: {:milliliter, value * 5}
  def to_milliliter({:tablespoon, value}), do: {:milliliter, value * 15}
  def to_milliliter(volume_pair), do: volume_pair

  def from_milliliter({:milliliter, value}, :cup), do: {:cup, value / 240}
  def from_milliliter({:milliliter, value}, :fluid_ounce), do: {:fluid_ounce, value / 30}
  def from_milliliter({:milliliter, value}, :teaspoon), do: {:teaspoon, value / 5}
  def from_milliliter({:milliliter, value}, :tablespoon), do: {:tablespoon, value / 15}
  def from_milliliter(volume_pair, _), do: volume_pair

  def convert(volume_pair, unit) do
    from_milliliter(to_milliliter(volume_pair), unit)
  end
end
```