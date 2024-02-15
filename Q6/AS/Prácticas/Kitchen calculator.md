[[Elixir]]

# Conversor de unidades de cocina
```elixir
defmodule KitchenCalculator do
  def get_volume(volume_pair) do
    {_, value} = volume_pair
    value
  end

  def to_milliliter(volume_pair) do
    {unit, value} = volume_pair
    cond do
      unit == :cup -> {:milliliter, value*240}
      unit == :fluid_ounce -> {:milliliter, value*30}
      unit == :teaspoon -> {:milliliter, value*5}
      unit == :tablespoon -> {:milliliter, value*15}
      true -> {:milliliter, value}
    end
  end

  def from_milliliter(volume_pair, unit) do
    {_, value} = volume_pair
    cond do
      unit == :cup -> {unit, value/240}
      unit == :fluid_ounce -> {unit, value/30}
      unit == :teaspoon -> {unit, value/5}
      unit == :tablespoon -> {unit, value/15}
      true -> {unit, value}
    end
  end

  def convert(volume_pair, unit) do
    from_milliliter(to_milliliter(volume_pair), unit)
  end
end
```