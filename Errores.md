[[Elixir]]

Ejercicios asociados:
+ [[RPN calculator]]
+ [[Circular buffer]]
+ [[Nth prime]]
+ [[Queen attack]]
+ [[Forth]]

# 1.Cacheado de errores
A veces en Elixir la metodología de dejar que rompa no es buena. Sin embargo, hay momentos en los que necesitamos controlar explícitamente cómo se manejan los errores para asegurar que nuestro código cumpla con ciertos contratos o requisitos.

Por convención cuando las funciones lanzan algún error se denotan con `!` al final del nombre. Por ejemplo, la función `Map.fetch/2`:
+ *`Map.fetch/2`:* devuelve `{:ok, value}` o `{:error}`.
+ *`Map.fetch!/2`:* genera un `KeyError` si la clave no está en el mapa.