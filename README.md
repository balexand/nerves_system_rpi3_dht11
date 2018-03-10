# Raspberry Pi 3 Model B with DHT11/DHT22 Device Tree Overlay

[![Hex version](https://img.shields.io/hexpm/v/nerves_system_rpi3_dht11.svg "Hex version")](https://hex.pm/packages/nerves_system_rpi3_dht11)

This is the base Nerves System configuration for the Raspberry Pi 3 Model B with support for the DHT11/DHT22 temperature and humidity sensor.

## Usage

Add the following dependency to your `mix.exs` file for the `"rpi3"` target:

```elixir
{:nerves_system_rpi3_dht11, ">= 0.0.0"}
```

Then install dependencies as usual.

### Reading temperature

TODO

### Reading humidity

TODO

## This is a fork of `nerves_system_rpi3`

See the [official `nerves_system_rpi3` README](https://github.com/nerves-project/nerves_system_rpi3) for more details. The version numbers of this project match those from the offical project.

### What did I change?

See these diffs to see how this project differs from the offical project:

* [1.0.0-rc.0](https://github.com/balexand/nerves_system_rpi3_dht11/compare/b952d2bb0472c3ff1ea92223fd12509fcdb864a7...v1.0.0-rc.0)
