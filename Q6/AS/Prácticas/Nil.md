[[Elixir]]

Ejercicios asociados:
+ [[Name badge]]
+ [[Binary search tree]]
+ [[Flatten array]]

# 1.El valor nulo
En elixir `nil` indica valor nulo, es decir, ausencia de valor.Es un átomo, pero generalmente se escribe `nil`, no `:nil`.

```elixir
favourite_song = nil

nil === :nil  # true
```

Podemos comprobar que una variable es nula usando `==` o usando `is_nil/1`.

```elixir
def call(phone_number) when is_nil(phone_number) do, :error
```

