[[Arquitectura do software]]

## Variables
Elixir es dinámicamente tipado.
```elixir
variable=10
variable="Hola"
```

El tipo de una variable se comprueba en tiempo de ejecución.
```elixir
variable = "Hola"
is_integer(variable) # Esto dará falso (false) ya que variable es una cadena, no un entero.
```

Se puede volver a asignar un valor a una variable.
```elixir
variable = 10
variable = variable + 5
```

## Módulos
Los módulos son la base de la organización del código en elixir. Se definen con `defmodule`.
```elixir
defmodule MathOperations do
  def add(a, b) do
    a + b
  end

  def subtract(a, b) do
    a - b
  end
end
```

Un módulo es visible para el resto de módulos:
```elixir
defmodule AnotherModule do
  def use_math_operations do
    IO.puts(MathOperations.add(5, 3)) # Podemos llamar a las funciones definidas en MathOperations
  end
end

AnotherModule.use_math_operations()
```

## Funciones
Las `named functions` deben ser definidas siempre en un módulo. Devuelven el valor de la última expresión. Se definen con `def`. 
```elixir
defmodule MathOperations do
  def add(a, b) do
    a + b
  end
end
```

Podemos hacer una función privada con `defp`.
```elixir
defmodule MathOperations do
  defp internal_add(a, b) do
    a + b
  end
end
```

Existe otra sintaxis en una sola línea.
```elixir
defmodule MathOperations do
  def add(a, b), do: a + b
end
```

Se invoca a las funciones con `Módulo.función()`.
```elixir
MathOperations.add(3, 5)
```

Dentro del propio módulo el nombre de este puede ser omitido.
```elixir
defmodule MathOperations do
  def add(a, b) do
    internal_add(a, b)  # Aquí, podemos omitir el nombre del módulo
  end

  defp internal_add(a, b) do
    a + b
  end
end
```

La aridad de una función es el número de argumentos que acepta.
```elixir
defmodule MathOperations do
  
	#add/2
  def add(a, b), do: a + b  # Esta función tiene una aridad de 2

	#add/3
  def subtract(a, b, c), do: a - b - c  # Esta función tiene una aridad de 3
end
```

## Integers y Strings
Los Integers sin número enteros sobre los que se pueden realizar operaciones matemáticas.
```elixir
a = 10
b = -5

addition_result = a + b            # Suma: 10 + (-5) = 5
subtraction_result = a - b         # Resta: 10 - (-5) = 15
multiplication_result = a * b      # Multiplicación: 10 * (-5) = -50
division_result = a / b            # División: 10 / (-5) = -2.0 (Elixir devuelve un float)

modulo_result = rem(a, b)          # Módulo: 10 rem (-5) = 0 (Resto de la división)
exponentiation_result = a ** b     # Exponente: 10 elevado a la -5ta potencia = 0.00001

integer_division_result = div(a, b)  # División entera: 10 div (-5) = -2 (cociente entero)

absolute_value_of_b = abs(b)       # Valor absoluto de b: abs(-5) = 5
```

Las Strings son secuencias de caracteres. Van entrecomilladas.
```elixir
string="Hola mundo!"
```

