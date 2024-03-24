[[Elixir]]

Ejercicios asociados:
+ [[RPN calculator inspection]]
+ [[Parallel letter frequency]]

# 1.Definición
Una tarea es un proceso diseñado para realizar una operación específica. No se comunican con otros procesos y devuelven un resultado al proceso que generó la tarea. Se utilizan para paralelizar el trabajo.

## 1.1.Async/await
Para iniciar una tarea, utiliza `Task.async/1`. Toma como argumento una función anónima y la ejecuta en un nuevo proceso que está enlazado al proceso llamador. Devuelve una estructura `%Task{}`.

Para obtener el resultado de la ejecución, pasa la estructura `%Task{}` a `Task.await/2`. Esperará a que la tarea termine y devolverá su resultado. El segundo argumento es un tiempo de espera en milisegundos, con un valor predeterminado de 5000.

## 1.2.Start/start_link
Si deseas iniciar una tarea solo para efectos secundarios, utiliza `Task.start/1` o `Task.start_link/1`. `Task.start/1` iniciará una tarea que no está enlazada al proceso que la llamó, y `Task.start_link/1` iniciará una tarea que está enlazada al proceso que la llamó. Ambas funciones devuelven una tupla `{:ok, pid}`.

```elixir
# Definir una función que realizará una tarea
task_function = fn ->
  IO.puts("Iniciando tarea...")
  :timer.sleep(3000) # Simular una operación que toma tiempo
  IO.puts("Tarea completada")
  :ok
end

# Iniciar una tarea y obtener la estructura de tarea
task = Task.async(task_function)

# Realizar otras operaciones mientras la tarea está en curso
IO.puts("Realizando otras operaciones mientras la tarea está en curso...")

# Esperar a que la tarea termine y obtener su resultado
result = Task.await(task)

# Utilizar el resultado de la tarea
IO.puts("Resultado de la tarea: #{inspect(result)}")
```