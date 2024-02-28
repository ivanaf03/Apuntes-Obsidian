[[Elixir]]

```elixir
defmodule RemoteControlCar do
  @enforce_keys [:nickname]
  defstruct [:nickname, battery_percentage: 100, distance_driven_in_meters: 0]

  def new(nickname \\ "none") do
    %RemoteControlCar{nickname: nickname}
  end

  def display_distance(%RemoteControlCar{}=remote_car) do
    "#{remote_car.distance_driven_in_meters} meters"
  end

  def display_battery(%RemoteControlCar{}=remote_car) when remote_car.battery_percentage == 0 do
    "Battery empty"
  end

  def display_battery(%RemoteControlCar{}=remote_car) do
    "Battery at #{remote_car.battery_percentage}%"
  end

  def drive(%RemoteControlCar{battery_percentage: 0}=remote_car) do
    remote_car
  end

  def drive(%RemoteControlCar{}=remote_car) do
    %{remote_car| battery_percentage: remote_car.battery_percentage - 1, distance_driven_in_meters: remote_car.distance_driven_in_meters + 20}
  end
end

```