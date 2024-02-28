[[Elixir]]

Ejercicios asociados:
+ [[Library fees]]
+ [[Gigasecond]]
+ [[Meetup]]

# 1.Módulos de fecha y hora
Elixir contiene 4 módulos para trabajar con el tiempo:
+ [>] *`Date`:* se crea con `~D[2024-01-01]`.
+ [>]  *`Time`:* se crea con `~T[10:00:00]`.
+ [>] *`NaiveDateTime`:* se crea con `~N[2024-01-01 10:00:00]`.
+ [>] *`DateTime`:* se crea con `DateTime.new!(~D[2021-01-01], ~T[12:00:00], "Etc/UTC")`.

## 1.1.Comparaciones de tiempo
No debemos usar los operadores de comparación. En su lugar podemos utilizar las funciones `compare/2` y `diff/2`.

```elixir
Date.compare(~D[2020-11-30], ~D[2020-12-01])  # :lt

Time.diff(~T[13:45:00], ~T[13:46:30])  # -90
```

## 1.2.Movimiento en el tiempo
Podemos añadir o quitar segundos mediante la función `add/2`.

```elixir
Time.add(~T[12:00:00], -1)  # ~T[11:59:59.000000]

NaiveDateTime.add(~N[2021-01-01 12:00:00], 4 * 24 * 60 * 60 + 30)  # ~N[2021-01-05 12:00:30] 
```

## 1.3.Conversiones
Existen varias funciones que permiten pasar de unos tipos temporales a otros.

```elixir
NaiveDateTime.to_date(~N[2021-01-01 12:00:00])  # ~D[2021-01-01]

NaiveDateTime.to_time(~N[2021-01-01 12:00:00])  # ~T[12:00:00]

NaiveDateTime.new!(~D[2021-01-01], ~T[12:00:00])  # ~N[2021-01-01 12:00:00]
```

