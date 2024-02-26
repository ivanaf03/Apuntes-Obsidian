[[Elixir]]

Ejercicios asociados:
+ [[Paint by number]]
+ [[Variable length quantity]]

# 1.Definición
Son una construcción que permiten manejar con comodidad binarios. Se construyen con `<< >>`.

```elixir
<<1, 0, 1, 1>> # bitstring de 4 bits con valores 1011
```

Podemos especificar el tamaño utilizando `:: size()`.

```elixir
<<1, 0, 1, 1>> :: size(4)
```

Un bitstring puede contener datos de diferentes tipos.

```elixir
<<1::size(1), 0::size(1), 1::size(1), 1::size(1), 42::size(8), 3.14::size(64)>>
# => <<178, 164, 0, 145, 235, 133, 30, 184, 81, 15::size(4)>>
```

Puede usarse el pattern matching para guardar valores.

```elixir
<<_::32, remainder::bitstring>> = <<8::32, 3::8>>
# => <<0, 0, 0, 8, 3>> 

remainder 
# => <<3>>
```