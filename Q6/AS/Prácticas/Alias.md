[[Elixir]]

Ejercicios asociados:
+ [[Need for speed]]

# 1.Definición
Para compartir código entre diferentes módulos de Elixir del mismo proyecto se deben referenciar por el nombre completo. Sin embargo, esto puede ser muy largo y tedioso.

Los `alias` permiten acortar los nombres, tanto cogiendo el módulo más interno como cambiándolo a nuestro gusto mediante `as:`.

```elixir
defmodule MyApp.MyModule do
  alias MyApp.Logger.Settings

  def get_logger_level do
    Settings.get_level()
  end
end
```

```elixir
defmodule Square do 
	alias Integer, as: I 
	
	def area(a), do: I.pow(a, 2) 
end
```