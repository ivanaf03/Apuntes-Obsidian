[[Elixir]]

Ejercicios asociados:
+ [[RPN calculator inspection]]
# 1.Procesos bidireccionales
Los procesos en elixir están aislados y no comparten datos. Cuando un proceso hijo se muere el padre no se ve afectado. Esto puede cambiarse linkeando procesos. Son bidireccionales.

Para ello podemos usar `spawn_link/1`. También podemos linkearlos más tarde usando `Process.link/1`. Puede ser util para paralelizar trabajo.

## 1.1.Captura de salidas
Cuando dos procesos en Elixir están enlazados entre sí, significa que si uno de los procesos falla y termina de manera inesperada, el otro proceso recibirá una notificación sobre esta falla en forma de un mensaje. Esto se logra utilizando la función `Process.flag(:trap_exit, true)` para configurar un proceso para que capture estas notificaciones de falla.

Cuando un proceso está configurado para capturar estas notificaciones, no se detendrá automáticamente si un proceso vinculado falla. En su lugar, recibirá un mensaje que sigue el patrón `{:EXIT, from, reason}`, donde `from` es el PID del proceso que falló y `reason` es la razón de la falla. Si `reason` no es igual al átomo `:normal`, indica que el proceso falló o fue detenido de manera forzada. Esto permite que el proceso que recibió la notificación maneje la falla de manera apropiada, por ejemplo, reiniciando el proceso fallido.

```elixir
defmodule Ejemplo do
  def proceso_hijo do
    # Configurar el proceso para capturar notificaciones de salida
    Process.flag(:trap_exit, true)
    
    # Simular una falla
    raise "Algo salió mal"
  end

  def proceso_padre do
    # Spawn del proceso hijo y vinculación bidireccional
    hijo_pid = spawn_link(&proceso_hijo/0)

    # Esperar la notificación de salida del proceso hijo
    receive do
      {:EXIT, pid, reason} ->
        IO.puts "El proceso hijo con PID #{inspect pid} ha fallado por la razón: #{inspect reason}"
    end
  end
end

# Ejecutar el proceso padre
Ejemplo.proceso_padre()

```