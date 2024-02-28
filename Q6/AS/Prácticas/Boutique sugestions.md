[[Elixir]]

```elixir
defmodule BoutiqueSuggestions do
  def get_combinations(tops, bottoms, options \\ []) do
    for x <- tops,
        y <- bottoms,
        x.base_color != y.base_color,
        x.price + y.price <= Keyword.get(options, :maximum_price, 100) do
      {x, y}
    end
  end
end

```