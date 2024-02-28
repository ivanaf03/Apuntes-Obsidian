[[Elixir]]

```elixir
defmodule LibraryFees do
  def datetime_from_string(string) do
    NaiveDateTime.from_iso8601!(string)
  end

  def before_noon?(datetime) do
    Time.before?(NaiveDateTime.to_time(datetime), ~T[12:00:00])
  end

  def return_date(checkout_datetime) do
    if before_noon?(checkout_datetime) do
      Date.add(NaiveDateTime.to_date(checkout_datetime), 28)
    else
      Date.add(NaiveDateTime.to_date(checkout_datetime), 29)
    end
  end

  def days_late(planned_return_date, actual_return_datetime) do
    actual = NaiveDateTime.to_date(actual_return_datetime)
    if Date.before?(planned_return_date, actual) do
      Date.diff(actual, planned_return_date)
    else
      0
    end
  end

  def monday?(datetime) do
    Date.day_of_week(datetime, :monday) == 1
  end

  def calculate_late_fee(checkout, return, rate) do
    days = days_late(return_date(datetime_from_string(checkout)), datetime_from_string(return))
    if monday?(datetime_from_string(return)) do
      div(days * rate, 2)
    else
      days * rate
    end
  end
end

```