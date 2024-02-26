[[Elixir]]

Ejercicios asociados:
+ [[Log parser]]
+ [[SGF parsing]]
+ [[Acronym]]
+ [[Run-length encoding]]
+ [[ISBN verifier]]
+ [[Isogram]]
+ [[Word count]]
+ [[Grep]]
+ [[Phone number]]
+ [[Markdown]]
+ [[Forth]]

# 1.PCRE
La PCRE son las Perl Compatible Regular Expressions. Son una serie de patrones que representan cualquier palabra. Las expresiones regulares en elixir se crean con `~r`. 

Podemos utilizar el operador `=~` para ver si una string pertenece a una expresión regular.

```elixir
"this is a test" =~ ~r/test/  # true
```

## 1.1.Sintaxis
Las expresiones regulares se crean entre las barras de `~r//`. Pueden contener:
+ [>] *Caracteres libres:* /abc/ coincide con "abc".
+ [>] *Caracteres especiales:* /a\\?/ coincide con "a?".
+ [>] *Números o letras:* /\\d{3}/ coincide con 3 dígitos,  /\\w+/ coincide con una o más letras o dígitos consecutivos.
+ [>] *Alteraciones:* /gato|perro/ coincide con "gato" o con "perro".
+ [>] *Cuantificadores:* /a{2,4}/ coincide con de 2 a 4 "a", /b*/ coincide con cero o más "b", /c?/ coincide con cero o una "c".
+ [>] *Grupos:* /(abc)+/ coincide con "abc", con "abcabc"...

## 1.2.Captura
La captura consiste en extraer una porción de una string. Para capturarla creamos un grupo y usamos `Regex.run/2`.

```elixir
Regex.run(~r/Weight: (\d*)g/, "Weight: 150g")
# => ["Weight: 150g", "150"]
```

Las capturas se pueden usar para substituir valores de una string con una expresión regular. Para ello usamos `Regex.replace/3`.

```elixir
Regex.replace(~r/Weight: (\d*)g/, "Weight: 150g", "Gewicht: \\1g") 
# => "Gewicht: 150g"
```

Podemos hacer algo similar a run con `Regex.named_capture/2`. En vez de una lista devuelve un mapa con las capturas nombradas por ?\<nombre>.

```elixir
Regex.named_captures(~r/Weight: (?<weight>\d*)g/, "Weight: 150g") #
=> %{"weight" => "150"}
```

## 1.3.Modificadores
Algunos modificadores que se pueden poner al final de las expresiones regulares son:
+ [>] *i:* no es sensible a mayúsculas.
+ [>] *u:* acepta unicode. 

```elixir
"ö" =~ ~r/^\w$/  # false 

"ö" =~ ~r/^\w$/u  # true


"A" =~ ~r/a/ #  false 
"A" =~ ~r/a/i #  true
```

## 1.4.Interpolación
Las expresiones regulares permiten interpolación.

```elixir
anchor = "$"  # final de línea

regex = ~r/end of the line#{anchor}/
"end of the line?" =~ regex  # false
"end of the line" =~ regex  # true
```

# 2.Módulo String
Muchas veces podemos usar funciones del módulo String en vez de expresiones regulares. Esto facilita mucho las cosas y es más rápido computacionalmente.

```elixir
# Expresiones regulares
regex = ~r/rojo/
texto = "El coche es rojo y el cielo también es rojo"
nuevo_texto = Regex.replace(regex, texto, "azul")
IO.puts(nuevo_texto)

# Módulo String
texto = "El coche es rojo y el cielo también es rojo"
nuevo_texto = String.replace(texto, "rojo", "azul")
IO.puts(nuevo_texto)

```

```elixir
# Expresiones regulares
if "YELLING!" =~ ~r/!$/, do: "Whoa, chill out!"

# Módulo String
if String.ends_with?("YELLING!", "!"), do: "Whoa, chill out!"
```