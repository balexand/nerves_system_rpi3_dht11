# Raspberry Pi 3 Model B with DHT11/DHT22 Device Tree Overlay

[![Hex version](https://img.shields.io/hexpm/v/nerves_system_rpi3_dht11.svg "Hex version")](https://hex.pm/packages/nerves_system_rpi3_dht11)

This is the base Nerves System configuration for the Raspberry Pi 3 Model B with support for the DHT11/DHT22 temperature and humidity sensor.

## Usage

Add the following dependency to your `mix.exs` file for the `"rpi3"` target:

```elixir
{:nerves_system_rpi3_dht11, ">= 1.0.0-rc"}
```

Then install dependencies as usual.

Temperature and relative humidity can be measured by reading a device file. For example:

```elixir
def temp_in_c do
  dht_read("/sys/bus/iio/devices/iio:device0/in_temp_input")
end

def relative_humidity_percent do
  dht_read("/sys/bus/iio/devices/iio:device0/in_humidityrelative_input")
end

defp dht_read(path) do
  case File.read(path) do
    {:ok, str} ->
      value = (str |> String.trim |> String.to_integer) / 1000
      {:ok, value}
    {:error, _} ->
      # This error happens often. If your app has a GenServer that polls the
      # sensor then you'll want to poll the sensor again after a short delay.
      :error
  end
end
```

## This is a fork of `nerves_system_rpi3`

See the [official `nerves_system_rpi3` README](https://github.com/nerves-project/nerves_system_rpi3) for more details. The version numbers of this project match those from the offical project.

### What did I change?

See these diffs to see how this project differs from the offical project:

* [1.0.0-rc.0](https://github.com/balexand/nerves_system_rpi3_dht11/compare/b952d2bb0472c3ff1ea92223fd12509fcdb864a7...v1.0.0-rc.0)
