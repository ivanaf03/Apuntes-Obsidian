[[Elixir]]

```elixir
defmodule ZebraPuzzle do
  @doc """
  Determine who drinks the water
  """
  @spec drinks_water() :: atom
  def drinks_water() do
    mapping()
    |> Enum.find(fn map -> map[:drink] == :water end)
    |> Map.get(:nationality)
  end
  @doc """
  Determine who owns the zebra
  """
  @spec owns_zebra() :: atom
  def owns_zebra() do
    mapping()
    |> Enum.find(fn map -> map[:pet] == :zebra end)
    |> Map.get(:nationality)
  end

  defp mapping() do
    [
      %{nationality: :norwegian, house: :yellow, pet: :fox, drink: :water, smoke: :kools},
      %{nationality: :ukranian, house: :blue, pet: :horse, drink: :tea, smoke: :chester},  
      %{nationality: :englishman, house: :red, pet: :snails, drink: :milk, smoke: :old},
      %{nationality: :spaniard, house: :ivory, pet: :dog, drink: :orange_juice, smoke: :lucky},
      %{nationality: :japanese, house: :green, pet: :zebra, drink: :coffee, smoke: :parlia}
    ]
  end
end

```