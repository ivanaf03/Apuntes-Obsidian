[[Elixir]]

Ejercicios asociados:
+ [[Lucas numbers]]
# 1.Operaciones lazy
El módulo `Stream` utiliza una política `eager`. Es decir, cuando se trabaja con sus operaciones cada una de ellas genera un resultado inmediato.

Una alternativa es usar el módulo `Stream`. Ofrece más o menos las mismas funcionalidades que `Enum`, pero de forma `lazy`. Solo se ejecutan una vez que el stream se envía a la función del módulo `Enum`. Implementa enumerable y  composable.

```elixir
stream = Stream.iterate(0, &(&1 + 1))
Enum.take(stream, 5)  # Toma los primeros 5 elementos del stream
# Output: [0, 1, 2, 3, 4]
```

```elixir
stream = Stream.iterate(0, &(&1 + 1))
       |> Stream.map(&(&1 * &1))
       |> Enum.take(5)
# Output: [0, 1, 4, 9, 16]
```