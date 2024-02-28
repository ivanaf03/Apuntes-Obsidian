[[Elixir]]

Ejercicios asociados:
+ [[Newsletter]]
+ [[Grep]]

# 1.El módulo File
El módulo `File` contiene funciones que nos permiten trabajar con ficheros. Podemos leer un fichero con `read/1` y escribir en el con `write/2`. 

Cuando escribimos en un fichero se abre un file descriptor y un nuevo proceso comienza a ejecutarse. Hay que tener cuidado cuando se escribe en bucle.

Con `open/2` podemos especificar si queremos abrir el fichero para escritura o lectura. Para escribir podemos usar el módulo `IO`.

Al acabar de trabajar con ficheros se deben cerrar con `close/1`.

```elixir
defmodule FileManager do
  # Función para escribir en un archivo
  def write_to_file(filename, data) do
    {:ok, file} = File.open(filename, [:write])
    IO.write(file, data)
    File.close(file)
  end

  # Función para leer un archivo
  def read_from_file(filename) do
    {:ok, file} = File.open(filename, [:read])
    data = IO.read(file, :all)
    File.close(file)
    data
  end
end

# Ejemplo de uso:
file_name = "ejemplo.txt"
data_to_write = "¡Hola mundo desde Elixir!"

# Escribir en el archivo
FileManager.write_to_file(file_name, data_to_write)

# Leer desde el archivo
data_read = FileManager.read_from_file(file_name)
IO.puts("Contenido del archivo:")
IO.puts(data_read)
```