[[Elixir]]

Ejercicios asociados:
+ [[Basketball website]]

# 1.Acceso a mapas
Una forma muy cómoda de devolver valores en los mapas es mediante el access behavior. Permite de una forma simple acceder a un valor de un mapa mediante su clave.

```elixir
my_map = %{key: "my value"}
your_map = %{"key" => "your value"}

my_map[:key] == "my value" # access behavior
your_map[:key] == nil
your_map["key"] == "your value"
```

Si no existe la key devuelve `nil`.