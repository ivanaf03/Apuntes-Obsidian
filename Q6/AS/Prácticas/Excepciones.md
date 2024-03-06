[[Elixir]]

Ejercicios asociados:
+ [[Stack underflow]]
+ [[Queen attack]]
+ [[Forth]]

# 1.Exception behavior
Las excepciones de elixir siguen el `Exception behavior`, que es similar al `Access behavior`. Define los errores y los trata:
+ [>] El nombre del módulo es el nombre del error.
+ [>] El módulo tiene una estructura de error.
+ [>] La estructura tiene un `:message`.
+ [>] El módulo puede usarse con `raise/1` o `raise/2`.

$\space$
Se definen dos excepciones, `message/1` y `exception/1`. Si no están implementadas se usarán las por defecto. 

## 1.1.Definir excepciones
Para definir las excepciones se usa la macro `defexception`.

```elixir
# Define un error mínimo, con el nombre `MyError`
defmodule MyError do
  defexception message: "error"
end

# Define un error con una función `exception/1` personalizada
defmodule MyCustomizedError do
  defexception message: "custom error"

  @impl true
  def exception(value) do
    case value do
      [] ->
        %MyCustomizedError{}

      _ ->
        %MyCustomizedError{message: "Alerta: " <> value}
    end
  end
end
```

## 1.2.Uso de excepciones 
Las excepciones definidas se pueden lanzar como errores mediante `raise/1` o `raise/2`.

```elixir
defmodule MyError do
  defexception message: "Este es un error personalizado"
end

defmodule MyCustomError do
  defexception message: "Otro tipo de error personalizado"

  @impl true
  def exception(value) do
    %MyCustomError{message: "Alerta: " <> value}
  end
end


# Usando raise/1 para levantar un error específico
raise MyError

# Usando raise/2 para levantar un error específico con atributos
raise MyCustomError, "Algo salió mal"

# También podemos pasar atributos adicionales
raise MyCustomError, message: "Algo salió mal"

# Si queremos usar una cadena como mensaje, se generará un RuntimeError
raise "Este es un error de tiempo de ejecución"

```