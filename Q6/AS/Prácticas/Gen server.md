[[Elixir]]

Ejercicio asociados:
+ [[Take a number deluxe]]
+ [[Circular buffer]]
+ [[React]]

# 1.Definición
El GenServer es un comportamiento que sirve como abstracción para la arquitectura cliente-servidor en Elixir. Es una abstracción de bucle de `receive`. Hace que sea mucho más simple mantener el estado.

Define varias callbacks, `init/1`, `handle_call/3`, `handle_cast/2` y `handle_info/3`. Los clientes no utilizan las llamadas directamente, sino que usan el módulo GenServer.

```elixir
defmodule AnnoyingPassengerAutoresponder do
  use GenServer

  # API para el Cliente

  def start_link(init_arg) do
    GenServer.start_link(__MODULE__, init_arg)
  end

  def are_we_there_yet?(pid) do
    GenServer.call(pid, :are_we_there_yet?)
  end

  # Callbacks del Servidor

  @impl GenServer
  def init(_init_arg) do
    # El contador inicial de preguntas siempre es 0
    state = 0
    {:ok, state}
  end

  @impl GenServer
  def handle_call(:are_we_there_yet?, _from, state) do
    reply =
      case state do
        s when s <= 3 -> "No."
        s when s <= 10 -> "Te he dicho #{s} veces ya. No."
        _ -> "..."
      end

    # Aumentar el contador de preguntas
    new_state = state + 1
    # Responder al solicitante
    {:reply, reply, new_state}
  end
end
```

## 1.1.Callbacks
Los principales callbacks de GenServer son:
+ [>] *`init/1`:* se ejecuta cuando se inicia el servidor. Se utiliza para inicializar el estado del servidor y puede devolver `{:ok, state}` para indicar que el servidor se inició correctamente, o `{:stop, reason}` para indicar que ha ocurrido un error y el servidor no debe iniciarse.
+ [>] *`handle_call/3`:* maneja mensajes síncronos que requieren una respuesta. Se ejecuta cuando se llama a `GenServer.call/2`. Recibe el mensaje, el pid del proceso que llama y el estado actual del servidor como argumentos. Debe devolver `{:reply, reply, new_state}` donde `reply` es la respuesta al mensaje y `new_state` es el nuevo estado del servidor.
+ [>] *`handle_cast`:*  maneja mensajes asíncronos que no requieren una respuesta. Se ejecuta cuando se llama a `GenServer.cast/2`. Recibe el mensaje y el estado actual del servidor como argumentos. Normalmente devuelve `{:noreply, state}`.
+ [>] *`handle_info/2`:*  maneja mensajes que no son enviados mediante `GenServer.call/2` o `GenServer.cast/2`, como los mensajes enviados con `send/2`. Funciona de manera similar a `handle_cast/2` y se utiliza para manejar mensajes inesperados.

## 1.2.Timeouts
Sirven para especificar un tiempo máximo de espera para recibir un mensaje en el buzón del proceso del servidor. Esto se logra mediante la adición de un elemento adicional a la tupla de retorno de cada uno de los callbacks (`init/1`, `handle_call/3`, `handle_cast/2`, y `handle_info/2`). Este elemento adicional es simplemente un número entero que representa el tiempo máximo de espera en milisegundos.

Por ejemplo, en lugar de devolver `{:ok, state}` desde `init/1`, podrías devolver `{:ok, state, timeout}` donde `timeout` es el tiempo máximo de espera.

# 2.Ejemplo

```elixir
defmodule TimeoutExample do
  use GenServer

  # Cliente API

  def start_link(timeout \\ 5000) do
    # Iniciar el GenServer y pasar el tiempo de espera como argumento de inicialización
    GenServer.start_link(__MODULE__, timeout)
  end

  def fetch_data(pid) do
    # Llamar al GenServer para solicitar datos
    GenServer.call(pid, :fetch_data)
  end

  # Callbacks del Servidor

  @impl GenServer
  def init(timeout) do
    # Inicializar el estado del servidor
    {:ok, %{data: nil, timeout: timeout}}
  end

  @impl GenServer
  def handle_call(:fetch_data, _from, state) do
    # Devolver el estado actual si ya tenemos datos
    if state[:data] != nil do
      {:reply, {:ok, state[:data]}, state}
    else
      # Si no hay datos, programar un temporizador para el tiempo de espera
      Process.send_after(self(), :timeout, state[:timeout])
      {:noreply, state}
    end
  end

  @impl GenServer
  def handle_info(:timeout, state) do
    # Manejar la expiración del temporizador
    {:reply, {:error, :timeout}, Map.put(state, :data, :timeout)}
  end
end

```