[[Elixir]]

Ejercicios asociados:
+ [[Freelancer rates]]
+ [[Complex numbers]]
+ [[Space Age]]

# 1.Números en Elixir
Hay dos tipos de números en elixir:
+ [>] Enteros
+ [>] Flotantes

```elixir
entero = 10

flotante = 3.14

flotante_cientifico = 1.23e-2

resultado = 1.23e4 == 12300  # true
```

Ambos tienen su módulo asociado, `Integer` y `Float`. Además se puede trabajar mezclándolos. Una expresión que combine enteros y flotantes siempre devuelve flotantes.

```elixir
resultado = 5 + 3.5
IO.puts("El resultado es: #{resultado}")  # El resultado es: 8.5
```

## 1.1.Errores de redondeo
Los flotantes suelen dar muchos fallos al redondear los resultados. Esto ocurre porque los números flotantes en binario en las máquinas solo son exactos cuando el denominador de la fracción es potencia de 2.

```elixir
0.1 + 0.2  # 0.30000000000000004
```

# 2.Operaciones
## 2.1.Comparación
Existen dos tipos de igualdades:
+ *Igualdad básica:* con el símbolo `==`, dice que 1 == 1.0 es cierto.
+ *Igualdad estricta:* con el símbolo `===`, dice que 1 === 1.0 es falso.

## 2.2.División
Una división entre dos enteros con el operador `/` siempre devuelve un flotante.

```elixir
4/4  # 1.0
```

Podemos realizar una división entera con la función `div/2`.

## 2.3.Conversiones
Podemos redondear los flotantes a enteros mediante las funciones `round/1`, `ceil/1` y `floor/1`. Si queremos convertirlos a flotantes podemos usar estas mismas funciones del módulo `Float`.

```elixir
ceil(5.2)  # 6

Float.ceil(5.2)  # 6.0
```

También podemos usar la función `trunc/1`. Elimina los decimales y devuelve un entero.

```elixir
trunc(5.2)  # 5
```
