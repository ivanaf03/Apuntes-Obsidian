[[Elixir]]

```elixir
defmodule LogLevel do
  def to_label(level, legacy?) do
    cond do
      level == 0 and not legacy? -> :trace
      level == 1 -> :debug
      level == 2 -> :info
      level == 3 -> :warning
      level == 4 -> :error
      level == 5 and not legacy? -> :fatal
      true -> :unknown
    end
  end

  def alert_recipient(level, legacy?) do
    value = to_label(level, legacy?)
    cond do
      value == :error or value == :fatal -> :ops
      value == :unknown and legacy? -> :dev1
      value == :unknown -> :dev2
      true -> false
    end
  end
end
```

