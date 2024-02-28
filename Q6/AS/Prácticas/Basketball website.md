[[Elixir]]

```elixir
defmodule BasketballWebsite do
  def extract_from_path(data, path) do
    list = String.split(path, ".")
    extract(data, list)
  end

  defp extract(_data, path) when path == [], do: nil

  defp extract(data, path) do
    [h|t] = path
    if path == [h] do
      data[h]
    else
      extract(data[h], t)
    end
  end

  def get_in_path(data, path) do
    get_in(data, String.split(path, "."))
  end
end

```