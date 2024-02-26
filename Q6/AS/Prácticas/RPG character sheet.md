[[Elixir]]

```elixir
defmodule RPG.CharacterSheet do
  def welcome() do
    IO.puts("Welcome! Let's fill out your character sheet together.")
  end

  def ask_name() do
    out = IO.gets("What is your character's name?\n")
    String.trim(out)
  end

  def ask_class() do
    out = IO.gets("What is your character's class?\n")
    String.trim(out)
  end

  def ask_level() do
    out = IO.gets("What is your character's level?\n")
    String.to_integer(String.trim(out))
  end

  def run() do
    welcome()
    name = ask_name()
    class = ask_class()
    level = ask_level()
    character_map = %{name: name, class: class, level: level}
    IO.inspect(character_map, label: "Your character")
  end
end
```
