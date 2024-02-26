[[Elixir]]

```elixir
defmodule LogParser do
  def valid_line?(line) do
    Regex.match?(~r/^\[(DEBUG|INFO|ERROR|WARNING)\]/, line)
  end

  def split_line(line) do
    Regex.split(~r/<[~*=~-]*>/, line)
  end

  def remove_artifacts(line) do
    Regex.replace(~r/end-of-line\d+/i, line, "")
  end
  
  def tag_with_user_name(line) do
    case Regex.run(~r/User\s+([^\s]+)/, line) do
      [_, user] -> "[USER] #{user} #{line}"
      _ -> line
    end
  end
end

```