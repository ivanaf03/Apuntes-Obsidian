[[Elixir]]

Ejercicios asociados:
+ [[Need for speed]]

# 1.Definición
El `import` permite usar funciones de un módulo externo sin llamarlo por el nombre de módulo. 

```elixir
defmodule MathUtils do
  def add(a, b) do
    a + b
  end

  def subtract(a, b) do
    a - b
  end
end
```

```elixir
defmodule MyApp.Calculator do
  import MathUtils

  def calculate(a, b) do
    result1 = add(a, b)
    result2 = subtract(a, b)
    {result1, result2}
  end
end
```

## 1.1.Conflictos
A veces importar un módulo entero puede dar conflictos de nombrado con funciones locales. Para evitarlo se pueden usar `:except` y `:only`, junto a la aridad de la función en una keyword list.

```elixir
defmodule MathUtils do
  def add(a, b) do
    a + b
  end

  def subtract(a, b) do
    a - b
  end

  def multiply(a, b) do
    a * b
  end
end
```

```elixir
defmodule MyApp.Calculator do
  import MathUtils, only: [subtract: 2, multiply: 2]
  
  def calculate(a, b) do
    result1 = subtract(a, b)
    result2 = multiply(a, b) 
    {result1, result2}
  end
end
```