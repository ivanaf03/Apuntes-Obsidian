[[Elixir]]

Ejercicios asociados:
+ [[RPN calculator]]

# 1.Recuperación de errores
Elixir tiene una forma de recuperar los errores que el código lance. Se utiliza `try-rescue`.

```elixir
defmodule Math do
  def divide(a, 0) do
    raise "No se puede dividir por cero"
  end

  def divide(a, b) do
    a / b
  end
end

# Uso del try/rescue para manejar errores
try do
  resultado = Math.divide(10, 0)
  IO.puts("El resultado de la división es #{resultado}")
rescue
  RuntimeError -> IO.puts("Ocurrió un error al dividir")
end
```

```elixir
try do
	raise RuntimeError, "error"
rescue 
	e in RuntimeError -> :error
end
```

