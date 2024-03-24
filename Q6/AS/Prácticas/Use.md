[[Elixir]]

Ejercicios asociados:
+ [[Dancing dots]]

# 1.Macro Use
El macro `use` nos permite extender rápidamente nuestro módulo con funcionalidad proporcionada por otro módulo. Cuando usamos un módulo, `use` puede inyectar código en el nuestro, por ejemplo, puede definir funciones, importar o alias otros módulos, o establecer atributos de módulo.

Se usa, por ejemplo, en los test.

```elixir
defmodule LasagnaTest do
  use ExUnit.Case

  test "expected minutes in oven" do
    assert Lasagna.expected_minutes_in_oven() === 40
  end
end

```

# 2.Macro Using
La macro `__using__/1` en Elixir se utiliza para definir qué sucede cuando un módulo usa otro módulo mediante el macro `use`. Esta macro toma un argumento, que es una lista de opciones pasadas al usar el módulo, y devuelve una expresión entre comillas que será insertada en el módulo que está utilizando el macro `use`.

Supongamos que tenemos un módulo llamado `Greeting`, que queremos usar en otros módulos para agregar funcionalidad de saludo. Definimos el módulo `Greeting` con un macro `__using__/1` para proporcionar la funcionalidad de saludo.

```elixir
defmodule Greeting do
  defmacro __using__(opts) do
    quote do
      def greet(name) do
        "Hello, #{name}!"
      end
    end
  end
end
```

```eiixir
defmodule MyModule do
  use Greeting

  def example_function do
    greet("John")
  end
end
```
