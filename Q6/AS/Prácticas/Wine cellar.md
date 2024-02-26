[[Elixir]]

```elixir
defmodule WineCellar do
  def explain_colors do
    [
      {:white, "Fermented without skin contact."},
      {:red, "Fermented with skin contact using dark-colored grapes."},
      {:rose, "Fermented with some skin contact, but not enough to qualify as a red wine."}
    ]
  end

  def filter(cellar, color, opts \\ []) do
    wines = Keyword.get_values(cellar, color)
    wines = filter_by_year(wines, Keyword.get(opts, :year))
    filter_by_country(wines, Keyword.get(opts, :country))
  end

  defp filter_by_year(wines, year) when is_integer(year) do
    Enum.filter(wines, fn {_, wine_year, _} -> wine_year == year end)
  end
  defp filter_by_year(wines, _), do: wines

  defp filter_by_country(wines, country) when is_binary(country) do
    Enum.filter(wines, fn {_, _, wine_country} -> wine_country == country end)
  end
  defp filter_by_country(wines, _), do: wines
end

```