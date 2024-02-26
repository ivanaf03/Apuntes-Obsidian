[[Elixir]]

```elixir
defmodule Ledger do
  @doc """
  Format the given entries given a currency and locale
  """
  @type currency :: :usd | :eur
  @type locale :: :en_US | :nl_NL
  @type entry :: %{amount_in_cents: integer(), date: Date.t(), description: String.t()}  
  @spec format_entries(currency(), locale(), list(entry())) :: String.t()
  def format_entries(_currency, locale, entries) when entries == [] do
    header_f(locale)
  end

  def format_entries(currency, locale, entries) do
    entries =
      Enum.sort(entries, fn a, b ->
        cond do
          a.date.day < b.date.day or a.description < b.description -> true
          a.date.day > b.date.day or a.description > b.description -> false
          true -> a.amount_in_cents <= b.amount_in_cents
        end
      end)
      |> Enum.map(fn entry -> format_entry(currency, locale, entry) end)
      |> Enum.join("\n")

    header_f(locale) <> entries <> "\n"
  end

  defp format_entry(currency, locale, entry) do
    year = to_string(entry.date.year)
    month = to_string(entry.date.month) |> String.pad_leading(2, "0")
    day = to_string(entry.date.day ) |> String.pad_leading(2, "0")
    date = date_f(year, month, day, locale) 

    number =  number_f(locale, entry)

    amount = amount_f(currency, locale, entry, number) |> String.pad_leading(14, " ")

    l = String.length(entry.description)
    description = description_f(entry, l)
    date <> "|" <> description <> " |" <> amount
  end

  defp header_f(locale) when locale == :en_US, do: "Date       | Description               | Change       \n"
  defp header_f(_locale), do: "Datum      | Omschrijving              | Verandering  \n"

  defp date_f(year, month, day, locale) when locale == :en_US, do: month <> "/" <> day <> "/" <> year <> " "
  defp date_f(year, month, day, _locale), do:  day <> "-" <> month <> "-" <> year <> " "

  defp number_f(locale, entry) when locale == :en_US do
    number_f2(locale, entry, ",", ".")
  end

  defp number_f(locale, entry) do
    number_f2(locale, entry, ".", ",")
  end

  defp number_f2(_locale, entry, a, b) do
    decimal = entry.amount_in_cents |> abs |> rem(100) |> to_string() |> String.pad_leading(2, "0")
    whole = 
      if abs(div(entry.amount_in_cents, 100)) < 1000 do
        abs(div(entry.amount_in_cents, 100)) |> to_string()
      else
        to_string(div(abs(div(entry.amount_in_cents, 100)), 1000)) <> a <> to_string(rem(abs(div(entry.amount_in_cents, 100)), 1000))
      end
    whole <> b <> decimal
  end

  defp amount_f(currency, locale, entry, number) when locale == :en_US and entry.amount_in_cents >= 0, do: "  #{if(currency == :eur, do: "€", else: "$")}#{number} "
  defp amount_f(currency, _locale, entry, number) when entry.amount_in_cents >= 0, do: " #{if(currency == :eur, do: "€", else: "$")} #{number} "
  defp amount_f(currency, locale, _entry, number) when locale == :en_US, do: " (#{if(currency == :eur, do: "€", else: "$")}#{number})"
  defp amount_f(currency, _locale, _entry, number), do: " #{if(currency == :eur, do: "€", else: "$")} -#{number} "

  defp  description_f(entry, l) when l > 26, do: " " <> String.slice(entry.description, 0, 22) <> "..."
  defp  description_f(entry, _l), do: " " <> String.pad_trailing(entry.description, 25, " ")

end
```