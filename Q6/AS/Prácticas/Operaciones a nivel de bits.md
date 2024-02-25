[[Elixir]]

Ejercicios asociados:
+ [[Secrets]]
+ [[Variable length quantity]]
+ [[Secret handshake]]
+ [[Allergies]]
+ [[Eliud's eggs]]

# 1.Sistemas de numeración
Elixir utiliza diferentes sistemas de numeración. Incluye binario, octal y hexadecimal. Los números se representan con el prefijo:
+ [>] *0b:* binario
+ [>] *0o:* octal
+ [>] *0x:* hexadecimal

```elixir
iex> binario = 0b1010
10
iex> octal = 0o10
8
iex> hexadecimal = 0xFF
255
```

## 1.1.Conversiones
Para convertir entre sistemas de numeración se pueden hacer con el módulo `Base`.
```elixir
iex> Base.decode16("FF")
255

iex> Base.encode16(255) 
"FF"
```

También se puede usar el módulo `Integer` para convertir números en base 
decimal a otras bases.
```elixir
iex> Integer.to_string(10, 2)
"1010"

iex> Integer.to_string(8, 8)
"10"

iex> Integer.to_string(255, 16)
"FF"
```

# 2.Módulo Bitwise
Es un módulo que contiene operaciones que nos permiten trabajar con enteros a nivel de bit. 
```elixir
Bitwise.band(0b1110, 0b1001)
# => 8 # 0b1000

Bitwise.bor(0b1110, 0b1001)
# => 13 # 0b1101

Bitwise.bxor(0b1110, 0b1001)
# => 7 # 0b0111

Bitwise.bnot(0b1110)
# => -15 # 0b11110001 (en complemento a dos)

Bitwise.bsl(0b1010, 2)
# => 40 # 0b101000 (desplazamiento a la izquierda)

Bitwise.bsr(0b1010, 2)
# => 2 # 0b10 (desplazamiento a la derecha)
```