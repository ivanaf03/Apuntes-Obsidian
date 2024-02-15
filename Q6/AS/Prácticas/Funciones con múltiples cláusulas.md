[[Elixir]]

# Principio abierto-cerrado
Elixir facilita las prácticas del Principio Abierto-Cerrado al permitir que las funciones tengan múltiples cláusulas, de modo que en lugar de tener una lógica de control dispersa y codificada de manera rígida, se pueden escribir funciones específicas para agregar o eliminar comportamientos fácilmente.

Las variables que no se usen se indican con una barrabaja delante.
```elixir
def number(n) when n == 7 do
  "Genial, ese es mi favorito"
end

def number(_n) do
  "Ese no es mi favorito"
end
```

# Guardias
Son expresiones booleanas que indican cuándo una cláusula debe ser ejecutada. Comienzan por `when`. 
```elixir
def f(n) when n>25 do
	IO.puts(n)
end
```

# Argumentos con valores por defecto
Se puede dar un valor por defecto a un argumento. Es útil cuando tenemos funciones con múltiples cláusulas. Se hace con `\\`.
```elixir
def number(n \\ 13)
def number(n) when n < 10, do: "¡Sueña más grande!"
def number(n) when n > 100, do: "No tan grande..."
```

```elixir
def example(a \\ 1, b \\ 2, c \\ 3) do
  "a: #{a}, b: #{b}, c: #{c}"
end

example()  # "a: 1, b: 2, c: 3"
example(10,20)  # "a: 10, b: 20, c: 3"
```