[[Elixir]]

Ejercicios asociados:
+ [[New passport]]

# 1.Definición
El `with` se utiliza para gestionar cadenas de operaciones que puedan producir resultados exitosos o fallar. Si todas las operaciones tienen éxito se ejecuta el `do`. Sino, ejecuta el `else`, que se suele usar para manejar los errores.

```elixir
defmodule Example do
  def divide(x, y) when y != 0 do
    {:ok, x / y}
  end

  def divide(_, _), do: {:error, "División por cero"}

  def calculate(x, y) do
    with {:ok, result1} <- divide(x, y),
         {:ok, result2} <- divide(y, result1) do
      {:ok, result2}
    else
      {:error, reason} -> {:error, reason}
    end
  end
end

IO.inspect Example.calculate(10, 2)    # => {:ok, 1.0}
IO.inspect Example.calculate(10, 0)    # => {:error, "División por cero"}

```