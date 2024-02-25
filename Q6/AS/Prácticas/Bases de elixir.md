[[Elixir]]

Ejercicios asociados:
+ [[Lasagna]]
+ [[Rational numbers]]

# 1.Estándares
Se suele usar `PascalCase` por convención para nombrar los módulos. Las variables y funciones suelen utilizar `snake_case`. 

Los comentarios se escriben precedidos de #. 

# 2.Variables
Elixir es un lenguaje dinámicamente tipado, lo que quiere decir que las variables se comprueban en tiempo de ejecución. Se le puede asignar un valor a una variable utilizando el operador `=`.

```elixir
x = 10
```

Son inmutables, una vez que se asigna un valor a una variable este no se cambia. Sin embargo, se pueden reasignar valores a las variables. Lo que ocurre realmente es que se crea una variable con el mismo nombre y un valor distinto.

Podemos asignar valores a variables mediante pattern matching.
```elixir
{x, y} = {10, 20}
```

## 2.1.Alcance
El alcance de las variables está determinado por el bloque en el que se definen. 
```elixir
def example_function do
  x = 10
  IO.puts(x)  # 10
end

example_function()
IO.puts(x)  # Error
```

# 3.Tipos de datos
## 3.1.Integers
Los `Integers` son aquellos datos sobre los cuales podemos realizar las operaciones matemáticas básicas. Estas son:
+ [>] *+:* suma
+ [>]  *-:* resta
+ [>]  *\*:* multiplicación
+ [>]  */:* división
+ [>]  *div/2:* división entera

## 3.2.Strings
Las `Strings` son secuencias de caracteres que van entrecomilladas.
```elixir
string="hola"
```

# 4.Módulos y funciones
## 4.1.Módulos
Los módulos son una unidad jerárquica similar a una clase en otros lenguajes. Un módulo es visible para otros módulos. Se definen con `defmodule`.

## 4.2.Funciones nombradas
Las funciones nombradas tienen que ser definidas dentro de un módulo. Se definen con `def` si son públicas y con `defp` si son privadas. Devuelven el valor de la última expresión.

Con `@spec` se definen los tipos de los argumentos y de retorno.

```elixir
defmodule BasicMath do
  @doc """
  Adds two numbers.
  """
  @spec add(number, number) :: number
  def add(a, b) do
    a + b
  end

  @doc """
  Multiplies two numbers.
  """
  @spec multiply(number, number) :: number
  def multiply(a, b) do
    a * b
  end
end
```

Existe otra nomenclatura más corta para las funciones.
```elixir
@spec multiply(number, number) :: number
def multiply(a, b), do: a * b
```

Se invocan con `módulo.función`.
```elixir
IO.puts(BasicMath.add(3, 5))      # Output: 8
IO.puts(BasicMath.multiply(3, 5)) # Output: 15
```

Las funciones del módulo Kernel no necesitan especificar el módulo al que pertenecen. Por ejemplo la función `div/2` mencionada antes.

## 4.2.1.Aridad
La aridad de una función es el número de argumentos que acepta. Se indica con `función/aridad`.
```elixir
def add(a,b,c), do a+b+c  # add/3
```



