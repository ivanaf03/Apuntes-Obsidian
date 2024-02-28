[[Elixir]]

```elixir
defmodule Newsletter do
  def read_emails(path) do
    {:ok, file} = File.open(path, [:read])
    data = IO.read(file, :all)
    File.close(file)
    String.split(data)
  end

  def open_log(path) do
     File.open!(path, [:write])
  end

  def log_sent_email(pid, email) do
    IO.puts(pid, email)
  end

  def close_log(pid) do
    File.close(pid)
  end

def send_newsletter(emails_path, log_path, send_fun) do
    log_file = open_log(log_path)

    emails = read_emails(emails_path)

    Enum.each(emails, fn email ->
      case send_fun.(email) do
        :ok ->
          log_sent_email(log_file, email)
        _ ->
          :error
      end
    end)
    close_log(log_file)
  end

end

```