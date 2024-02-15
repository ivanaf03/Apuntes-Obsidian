[[Elixir]]

# Convenciones
Se suele usar `PascalCase` por convención para nombrar los módulos. Las variables y funciones suelen utilizar `snake_case`. 

## Comentarios
Los comentarios se escriben precedidos de #. Se pueden hacer docs similares a Java.
```elixir
@doc """
Esto es un doc.
"""

# Esto es un comentario
```

# Tipado
Elixir es dinámicamente tipado. El tipo de las variables de comprueba en tiempo de ejecución.

Usamos el operador `=` para asignar un nombre a una variable. Se pueden reasignar valores a las variables.

## Enteros
Los `Integers` son aquellos datos sobre los cuales podemos realizar las operaciones matemáticas básicas.

+ [<] Operaciones:
+ *+:* suma
+ *-:* resta
+ *\*:* multiplicación
+ */:* división
+ *div():* división entera

## Strings
Las `Strings` son secuencias de caracteres que van entrecomilladas.
```elixir
string="hola"
```

# Módulos y funciones
## Módulos
Los módulos son una unidad jerárquica similar a una clase en otros lenguajes. Un módulo es visible para otros módulos. Se definen con `defmodule`.

## Funciones
Las `named functions` son funciones definidas dentro de un módulo. Se definen con `def` si son públicas y `defp` si son privadas. Devuelven el valor de la última expresión.

Con `@spec` se definen los tipos de los argumentos y de retorno.

```elixir
defmodule BasicMath do
  @doc """
  Adds two numbers.
  """
  @spec add(number, number) :: number
  def add(a, b) when is_number(a) and is_number(b) do
    a + b
  end

  @doc """
  Multiplies two numbers.
  """
  @spec multiply(number, number) :: number
  def multiply(a, b) when is_number(a) and is_number(b) do
    a * b
  end
end
```

Existe otra nomenclatura más corta para las funciones:
```elixir
@spec multiply(number, number) :: number
def multiply(a, b) when is_number(a) and is_number(b), do: a * b
```

Se invocan con `módulo.función`.
```elixir
IO.puts(BasicMath.add(3, 5))      # Output: 8
IO.puts(BasicMath.multiply(3, 5)) # Output: 15
```

### Aridad
La aridad de una función es el número de argumentos que acepta. Se indica con `función/aridad`.
```elixir
def add(a,b,c), do a+b+c  # add/3
```

# Libraría estándar
El módulo `Kernel` es el entorno por defecto de elixir. Proporciona las bases para el lenguaje. A partir de él se construyen los `Built-in types`. Estos a su vez forman los `Data types`. Suelen tener un módulo asociado.

