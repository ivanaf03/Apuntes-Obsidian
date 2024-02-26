[[Elixir]]

Ejercicios asociados:
+ [[German sysadmin]]
+ [[Nucleotide count]]
+ [[Pangram]]
+ [[RNA transcription]]
+ [[Rotational cipher]]
+ [[Atbash cipher]]
+ [[Simple cipher]]
+ [[Diamond]]

# 1.Definición
Las charlist son listas de enteros que representan el valor en Unicode del caracter correspondiente. Se representan con `~c`.

```elixir
~"hola"
```

Para saber el valor entero de un caracter podemos usar `?`. 

```elixir
?A  # 65
```

## 1.1.Charlists como listas
Las charlists son listas y se pueden usar como tal.

```elixir
~c"" === []
# => true

is_list(~c"hello")
# => true

[first_letter | _] = ~c"cat" 
first_letter
# => 99

~c"hi" ++ ~c"!"
# => ~c"hi!"
```

También permiten utilizar funciones del módulo `List`.

```elixir
List.first(~c"hello")
# => 104 

List.pop_at(~c"hello", 0) 
# => {104, ~c"ello"}
```

Si una lista contiene enteros que puedan ser representados se mostrarán como una charlist.

```elixir
[65, 66, 67]
# => ~c"ABC"
```

# 2.Printeabilidad
Si una lista de enteros contiene caracteres no printeables se muestra como lista en lugar de como charlist, aunque se definan utilizando la sintaxis `~c`. Para comprobarlo se usa `List.ascii_printeable/1`.

```elixir
# Verificar si una lista de enteros contiene solo caracteres ASCII imprimibles
List.ascii_printable?([65, 66, 67])         # Devuelve true
List.ascii_printable?([65, 66, 67, 0])      # Devuelve false

# Utilizando la sintaxis ~c"" para definir una lista de caracteres
~c"ABC\0"                                    # Se mostrará como [65, 66, 67, 0]

# Definición manual de la misma lista
[65, 66, 67, 0]                              # Se mostrará como [65, 66, 67, 0]
```

Utilizando `IO.inspect` podemos ver las dos formas de representación.

```elixir
IO.inspect(~c"ABC", charlists: :as_charlists)
# => prints ~c"ABC" 

IO.inspect(~c"ABC", charlists: :as_lists) 
# => prints [65, 66, 67]
```

# 3.Charlists y strings
Las charlist y las strings no son iguales. Las strings son binarios y las charlists listas de enteros.

```elixir
~c"hello" == "hello"  # false

IO.inspect(~c"tschüss", charlists: :as_lists)
# => prints [116, 115, 99, 104, 252, 115, 115]

IO.inspect("tschüss", binaries: :as_binaries)
# => prints <<116, 115, 99, 104, 195, 188, 115, 115>>
# En UTF-8 ü se codifica como 195 y 188
```

Podemos convertir una charlist a una string con `to_string/1`.

```elixir
to_string(~c"hello")
# => "hello"
```


