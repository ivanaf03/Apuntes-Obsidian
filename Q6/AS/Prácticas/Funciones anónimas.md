[[Elixir]]

# Uso de funciones anónimas
Una función anónima es una función que no tiene un nombre asociado y puede ser definida y utilizada en el momento y lugar en que es necesaria. 

+ [i] **Aparecen en:**
+ Asignadas a variables.
+ Como argumentos y valores de retorno.
+ Empleadas dinámicamente

## Nombrado
Se suelen crear con `fn`. Se accede a ellas con un punto. Por ejemplo:
```elixir
function_variable = fn n -> n + 1 end

IO.puts(function_variable.(1))  # 2
```

### Forma simplificada
Existe una forma más simple de crear funciones anónimas. Se usa el operador de captura &. El primer & declara el inicio de la expresión de captura y los argumentos se denotan como &1, &2... sucesivamente.
```elixir
# En lugar de:
fn x, y -> abs(x) + abs(y) end

# Podemos escribir:
&(abs(&1) + abs(&2))
```

Esto mismo se puede hacer para capturar `named functions`.
```elixir
defmodule Ejemplo do
  def suma(a, b) do
    a + b
  end
end

defmodule Ejemplo2 do
  def suma_x(a, b) do
    suma = &Ejemplo.suma/2  # captura
    suma.(a, b)
  end
end

IO.puts(Ejemplo2.suma_x(2, 3))
```