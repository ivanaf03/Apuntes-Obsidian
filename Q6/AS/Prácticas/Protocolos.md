[[Elixir]]

Ejercicios asociados:
+ [[Bread and potions]]
+ [[Clock]]

# 1.Polimorfismo
Los protocolos en elixir son un mecanismo que permite lograr polimorfismo. Se pueden crear diferentes implementaciones de funciones según los tipos de datos con los que se trabajen.

## 1.1.Definición
Se utiliza `defprotocol` para definir un protocolo. Contienen uno o varios encabezados de funciones.

```elixir
defprotocol Reversible do
  def reverse(term)
end
```

Para implementar un protocolo para un tipo de datos específico se utiliza `defimpl`. 

```elixir
defimpl Reversible, for: List do
  def reverse(term) do
    Enum.reverse(term)
  end
end
```

# 2.Ejemplo
```elixir
defprotocol MathOperations do
  def operate(a, b, operation)
end

defmodule MathExample do
  defimpl MathOperations, for: Integer do
    def operate(a, b, :add), do: a + b
    def operate(a, b, :subtract), do: a - b
    def operate(a, b, :multiply), do: a * b
    def operate(a, b, :divide), do: div(a, b)
  end

  defimpl MathOperations, for: Float do
    def operate(a, b, :add), do: a + b
    def operate(a, b, :subtract), do: a - b
    def operate(a, b, :multiply), do: a * b
    def operate(a, b, :divide), do: Float.round(a / b)
  end

  def example do
    # Operaciones con enteros
    IO.puts MathOperations.operate(5, 3, :add)      # => 8
    IO.puts MathOperations.operate(5, 3, :subtract) # => 2
    IO.puts MathOperations.operate(5, 3, :multiply) # => 15
    IO.puts MathOperations.operate(5, 3, :divide)   # => 1

    # Operaciones con flotantes
    IO.puts MathOperations.operate(5.0, 3.0, :add)      # => 8.0
    IO.puts MathOperations.operate(5.0, 3.0, :subtract) # => 2.0
    IO.puts MathOperations.operate(5.0, 3.0, :multiply) # => 15.0
    IO.puts MathOperations.operate(5.0, 3.0, :divide)   # => 2.0
  end
end
```