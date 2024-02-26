[[Elixir]]

```elixir
defmodule HighSchoolSweetheart do
  def first_letter(name) do
    name
    |> String.replace("\n", "")
    |> String.replace("\t", "")
    |> String.trim()
    |> String.at(0)
  end

  def initial(name) do
    initial = first_letter(name)
    initial
    |>String.upcase()
    |> Kernel.<>(".")
  end

  def initials(full_name) do
    [fst, snd] = String.split(full_name, " ")
    initial(fst)<>" "<>initial(snd)
  end

  def pair(full_name1, full_name2) do
    """
         ******       ******
       **      **   **      **
     **         ** **         **
    **            *            **
    **                         **
    **     #{initials(full_name1)}  +  #{initials(full_name2)}     **
     **                       **
       **                   **
         **               **
           **           **
             **       **
               **   **
                 ***
                  *
    """
  end
end
```