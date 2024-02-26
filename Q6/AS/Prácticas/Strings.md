[[Elixir]]

Ejercicios asociados:
+ [[Hearth]]
+ [[Affine cipher]]
+ [[Food chain]]
+ [[Anagram]]
+ [[Pig latin]]
+ [[Run-length encoding]]
+ [[Atbash cipher]]
+ [[Crypto square]]
+ [[Phone number]]
+ [[OCR numbers]]
+ [[Alphametics]]

# 1.Definición
Las String en elixir son cadenas de caracteres que se denotan entre `"`.

```elixir
string = "Hola"
```

Se pueden concatenar con el operador `<>`.

```elixir
"Hola" <> "Mundo"
```

Soportan interpolación, es decir, meter funciones o variables dentro de la propia String. Se hace con el operador `#{}`.

```elixir
value = "caballo"

"Tengo un #{value}."

"Esto es #{["una", " lista"]}."
```

Se puede usar `\` para representar caracteres como el salto de línea, el #, la ", etc.

```elixir
"Fin de línea.\n"
```

## 1.1.Bloques de texto
Con la notación `"""` podemos crear bloques de texto para poder escribir en varias líneas de forma más cómoda. 

```elixir
"""
línea 1
línea 2
"""
```

Se suele usar para documentar funciones y módulos.
```elixir
defmodule MyModule do
  @moduledoc """
  Este módulo contiene funciones para realizar operaciones básicas.
  """

  @doc """
  Suma dos números.

  ## Examples

      iex> MyModule.sum(2, 3)
      5

  """
  def sum(a, b) do
    a + b
  end
end
```

# 2.Módulo String
El módulo `String` contiene muchas funciones útiles para trabajar con Strings.

```elixir
# Convertir a minúsculas
String.downcase("PLEASE NO SHOUTING")
# => "please no shouting"

# Dividir una cadena en caracteres individuales y eliminar los espacios en blanco
String.split("hello", "", trim: true)
# => ["h", "e", "l", "l", "o"]

# Reemplazar una subcadena con otra
String.replace("Do I enjoy Elixir? Maybe...", "Maybe...", "Definitely!")
# => "Do I enjoy Elixir? Definitely!"

# Obtener el carácter en una posición específica de una cadena
String.at("12345", 2)
# => "3"
```

Las String empiezan en el índice 0. 
