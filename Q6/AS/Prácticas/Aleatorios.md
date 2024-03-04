[[Elixir]]

Ejercicios asociados:
+ [[Captain's log]]
+ [[D&D character]]
+ [[Simple cipher]]

# 1.Elegir elemento aleatorio
Para coger un elemento de un enumerable en Elixir podemos usar `Enum.random`. Elige un elemento al azar y lo devuelve.

```elixir
lista = [1, 2, 3, 4, 5]

elemento_aleatorio = Enum.random(lista)

IO.puts("El elemento aleatorio es: #{elemento_aleatorio}")
```

# 2.Generar un flotante aleatorio
Elixir no permite generar números flotantes directamente. Para ello podemos usar la función de Erlang `:rand.uniform/0`.

```elixir
# Generamos un número flotante aleatorio entre 0.0 y 1.0
numero_flotante_aleatorio = :rand.uniform()

IO.puts("El número flotante aleatorio es: #{numero_flotante_aleatorio}")

```