[[Elixir]]

Ejercicios asociados:
+ [[Freelancer rates]]
+ [[Resistor color trio]]
+ [[All your base]]
+ [[Armstrong numbers]]
+ [[Collatz conjecture]]
+ [[Nth prime]]
+ [[Leap]]
+ [[Largest series product]]
+ [[Luhn]]
+ [[Change]]
+ [[Square root]]

# 1.Módulo Integer
El módulo `Integer` proporciona muchas funciones para trabajar de forma cómoda con enteros. 

```elixir
# Ejemplos de todas las funciones del módulo Integer en Elixir

# digits(integer, base \\ 10)
Integer.digits(123) # Output: [1,2,3]

# extended_gcd(a, b)
Integer.extended_gcd(16, 24) # Output: {8, -1, 1}

# floor_div(dividend, divisor)
Integer.floor_div(10, 3) # Output: 3

# gcd(integer1, integer2)
Integer.gcd(16, 24) # Output: 8

# mod(dividend, divisor)
Integer.mod(10, 3) # Output: 1

# parse(binary, base \\ 10)
Integer.parse("123") # Output: {123, ""}

# pow(base, exponent)
Integer.pow(2, 3) # Output: 8

# to_charlist(integer, base \\ 10)
Integer.to_char_list(123) # Output: [49, 50, 51]

# to_string(integer, base \\ 10)
Integer.to_string(123) # Output: "123"

# undigits(digits, base \\ 10)
Integer.undigits([1, 2, 3]) # Output: 123
```

# 2.Notación
Los enteros muy grandes se suelen escribir poniendo `_` cada 3 dígitos.

```
1_000_000_000  # 1000000000
```

## 2.1.Otras bases
Elixir permite representar enteros en base decimal, binarios, octales y hexadecimales. Se usan los prefijos `0b`, `0o` y `0x`.

```elixir
0b0100  # 4

0o255  # 265

0xFF  # 255
```

