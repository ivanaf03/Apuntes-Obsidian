[[Elixir]]

Ejercicios asociados:
+ [[Hearth]]
+ [[Affine cipher]]
+ [[Acronym]]
+ [[Scrabble score]]
+ [[Series]]
+ [[Word count]]

# 1.Definición
El operador pipe sirve para encadenar funciones de forma que el argumento de salida de la función del lado izquierdo del pipe es el primer argumento de la función del lado derecho. Se hace con el operador `|>`.

```elixir
String.replace_suffix(String.upcase(String.duplicate("go ", 3))," ","!")

# Con pipes
"go "
|> String.duplicate(3)
|> String.upcase()
|> String.replace_suffix(" ", "!")
```

## 1.1.Interacción con el módulo Kernel
Cuando metemos funciones del módulo `Kernel` en los pipes es obligatorio poner delante el módulo.

```elixir
2 |> Kernel.*(3) |> Kernel.==(6)  # 2 * 3 == 6
```

# 2.Reglas estéticas
Generalmente en elixir los desarrolladores siguen ciertas reglas para que el código sea más legible:
+ [>] No usar pipes cuando solo se hace una función.
+ [>] No meter funciones anónimas dentro de pipes.
+ [>] Siempre empezar los pipes con variables, no con funciones. 