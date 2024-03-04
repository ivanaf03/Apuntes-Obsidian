[[Elixir]]

Ejercicios asociados:
+ [[Captain's log]]
+ [[Complex numbers]]

# 1.Librerías
No es recomendable escribir código en elixir que ya venga proporcionado por las librerías de Erlang. Algunas operaciones matemáticas o funciones relacionadas con el tiempo son funciones de Erlang.

# 1.1.Librería estándar
La librería estándar de Erlang se puede usar en Elixir directamente. Se llaman mediante átomos. Algunas muy usadas son las matemáticas.

```elixir
:math.pi()

:math.sin(:math.pi())

:math.cos(:math.pi())

:math.pow(2, 3)

:math.log2(100)

:math.log10(100)
```

Otras muy comunes a parte del número pi son la función `sleep` para dormir un proceso y la función para generar un flotante aleatorio.

```elixir
:timer.sleep(5000)  # 5 segundos

:rand.uniform()
```

### 1.1.1.Formateo de strings
Podemos utilizar la función `io_lib.format/2` para formatear strings. 

```elixir
# Formateamos un entero en base 16
:io_lib.format("~.16B", [255])
# Salida esperada: "FF"

# Formateamos un entero en base 2
:io_lib.format("~.2B", [10])
# Salida esperada: "1010"

# Formateamos un entero en base 8
:io_lib.format("~.3B", [100])
# Salida esperada: "144"

# Formateamos un número en notación científica
:io_lib.format("~.3e", [12345.6789])
# Salida esperada: "1.235e4"

# Formateamos un número flotante con 2 decimales de precisión
:io_lib.format("~.2f", [3.14159])
# Salida esperada: "3.14"

# Formateamos un entero como un carácter ASCII
:io_lib.format("~c", [65])
# Salida esperada: "A"

# Formateamos una cadena de texto
:io_lib.format("~s", ["Hello, world!"])
# Salida esperada: "Hello, world!"
```