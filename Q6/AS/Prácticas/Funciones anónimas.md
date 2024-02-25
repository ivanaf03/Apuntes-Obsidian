[[Elixir]]

Ejercicios asociados:
+ [[Secrets]]
+ [[Strain]]

# 1.Definición de funciones anónimas
Una función anónima es una función sin nombre que se puede definir y utilizar de forma inmediata, sin asignarlas a una variable o nombrarlas explícitamente.

## 1.1.Notación básica
La sintaxis básica es `fn param -> result end`.
```elixir
sumar = fn a, b -> a + b end
```

Pueden capturar valores de fuera de la función anónima que estén en el entorno de definición.
```elixir
x = 10
incrementar = fn y -> x + y end
IO.puts(incrementar.(5))  # 15
```

A veces es necesario definirlas en varios bloques usando la notación `do-block`.
```elixir
sumar = fn
  a, b -> 
    suma = a + b
    IO.puts("La suma es #{suma}")
    suma
end
sumar.(3, 4)  # La suma es 7
```

## 1.2.Notación simplificada
Existe una forma más simple de crear funciones anónimas. Se usa el operador `&`. Para representar los argumentos de la función se utilizan `placeholders`. Se representan como `&1`, `&2`, ..., `&n`.
```elixir
# En lugar de:
fn x, y -> abs(x) + abs(y) end

# Podemos escribir:
&(abs(&1) + abs(&2))
```

### 1.2.1.Captura de funciones
El operador `&` se conoce como operador de captura. Permite también capturar funciones nombradas.
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

IO.puts(Ejemplo2.suma_x(2, 3))  # 5
```