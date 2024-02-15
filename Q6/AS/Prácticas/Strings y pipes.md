[[Elixir]]

# Strings
Las String en Elixir se escriben entrecomilladas. El salto de línea se pone con `\n`.
```elixir
string="hola"
```

Se pueden concatenar con `<>`.
```elixir
"Buenos "<>"días"
```

Soportan la interpolación, es decir, permiten incluir expresiones dentro de Strings utilizando llaves.
```elixir
"6 * 7 = #{6 * 7}"
```

Con `"""` podemos crear bloques de texto.

## Pipe operator
El `|>` permite pasar el valor de una función a la siguiente. Funciona como los pipe de linux.
```elixir
"hello" 
|> String.upcase()
|> Kernel.<>("?!")
```