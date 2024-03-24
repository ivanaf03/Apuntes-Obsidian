[[Elixir]]

Ejercicios asociados:
+ [[Dancing dots]]

# 1.Definición
Los behaviours nos permiten definir interfaces en un módulo que puede ser interpretado por diferentes llamadas. 

Para definirlos se crea un módulo y se especifica una lista de funciones que forman parte de la interfaz deseada. Se utiliza la anotación `@callback`. 

```elixir
defmodule Contable do
  @callback contar(coleccion :: any) :: pos_integer
end
```

# 2.Implementación
Para agregar un comportamiento al módulo se utiliza la anotación `@behaviour`. Su valor es el nombre del módulo behaviour al que se llama. Después se definen las funciones que este comportamiento requiere.

```elixir
defmodule ColeccionDeLibros do
  @behaviour Contable

  defstruct [:lista, :propietario]

  @impl Contable
  def contar(coleccion) do
    Enum.count(coleccion.lista)
  end

  def marcar_como_leido(coleccion, libro) do
    # otra función no relacionada con el comportamiento Contable
  end
end

```

## 2.1.Implementaciones por defecto
Cuando definimos un comportamiento, es posible proporcionar una implementación predeterminada de una devolución de llamada. Esta implementación debe definirse en la expresión entre comillas del macro `using/1`.

Para hacer posible que los usuarios del módulo de comportamiento anulen la implementación predeterminada, llamamos al macro `defoverridable/1` después de la implementación de la función. Acepta una lista de palabras clave de nombres de funciones como claves y aridades de funciones como valores.

```elixir
defmodule Contable do
  @callback contar(coleccion :: any) :: pos_integer

  defmacro __using__(_) do
    quote do
      @behaviour Contable
      def contar(coleccion), do: Enum.count(coleccion)
      defoverridable contar: 1
    end
  end
end
```