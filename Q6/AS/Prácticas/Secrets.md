[[Elixir]]

# Ejercicio de funciones anónimas
```elixir
defmodule Secrets do
  def secret_add(secret) do
    fn a->a+secret end
  end

  def secret_subtract(secret) do
    fn a->a-secret end
  end

  def secret_multiply(secret) do
    fn a->a*secret end
  end

  def secret_divide(secret) do
    fn a->div(a,secret) end
  end

  def secret_and(secret) do
    fn a->Bitwise.band(a, secret) end
  end

  def secret_xor(secret) do
    fn a->Bitwise.bxor(a, secret) end
  end

  def secret_combine(secret_function1, secret_function2) do
    fn a->secret_function2.(secret_function1.(a)) end
  end
end
```