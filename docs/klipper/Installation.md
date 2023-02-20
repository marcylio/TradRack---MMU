# Installation

This document lists the steps to get Trad Rack set up to work with
Klipper.

## Klippy module

Place [trad_rack.py](../../Klipper_Stuff/klippy_module/trad_rack.py)
in `/klipper/klippy/extras` and restart the Klipper service to load the
module.

## Config files

### Using provided config files

Place the following files inside your Klipper config folder:

- [trad_rack_skr_pico.cfg](../../Klipper_Stuff/klipper_config/trad_rack_skr_pico.cfg):
  Base config file, meant for use with
  the BIGTREETECH SKR Pico board. This file is required.
  Make sure to make the following changes:
  - [mcu tr] section
    - Replace `serial` with the serial for your board.
      See Klipper's [Installation](https://www.klipper3d.org/Installation.html)
      document if you need helping finding this value.
  - [trad_rack] section
    - Change `toolhead_fil_sensor_pin` to match the pin your are using
    for your toolhead filament sensor.
    - Change `lane_count` to match your Trad Rack.
  - [stepper_tr_selector] section
    - Change `position_max` accordingly depending on your 
      `lane_count`.
  - [tmc2209 stepper_tr_selector] section
    - Change `run_current` to match your selector motor.
  - [tmc2209 stepper_tr_fil_driver] section
    - Change `run_current` to match your filament driver motor.
- [trad_rack_optional.cfg](../../Klipper_Stuff/klipper_config/trad_rack_optional.cfg):
  Optional config file. This file is recommended but may be more or
  less useful depending on your slicer setup.

### Building a config from scratch

See [Config Reference](Config_Reference.md) for the required
configuration sections and parameters for Trad Rack.