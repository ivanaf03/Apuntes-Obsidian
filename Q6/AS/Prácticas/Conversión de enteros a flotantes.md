[[Elixir]]

# Números en Elixir
Hay dos tipos de números en elixir.
+ [<] **Números:**
+ Enteros `integer=3`
+ Flotantes `float=3.14`

Ambos tienen su módulo asociado, `Integer` y `Float`. Además se puede trabajar mezclándolos. Una expresión que combine enteros y flotantes siempre devuelve flotantes.
```elixir
2*2  # 4
2*2.5 # 5
```

## División
Siempre devuelve flotantes.
```elixir
4/4  # 1.0
```

Se puede usar `trunc/1` para convertirlo a entero o usar la división entera `div/2`.
