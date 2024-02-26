[[Elixir]]

```elixir
defmodule Username do
  def sanitize(list) do
    case list do
      [] -> []
      [?ä | t] -> [?a, ?e | sanitize(t)]
      [?ö | t] -> [?o, ?e | sanitize(t)]
      [?ü | t] -> [?u, ?e | sanitize(t)]
      [?ß | t] -> [?s, ?s | sanitize(t)]
      [h | t] when (h >= ?a and h <= ?z) or h == ?_ -> [h | sanitize(t)]
      [_ | t] -> sanitize(t)
    end
  end
end
```