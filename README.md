# Modular Klipper for Railcore

This project is a modular Klipper configuration aimed at use with Railcore printers.

The Railcore is designed to be a platform for experimentation and, as such, there is a wide variety in hardware configurations making providing a single firmware configuration difficult. 

To help address this, this project splits Klipper configuration into a number of discrete includable modules, allowing the user to easily pick and choose components to match their build.

# Configuration Structure

There are three primary configuration files in this project:

* printer.cfg - the traditional Klipper configuration file. This has been reduced to the minimum configuration necessary to set up Klipper and the printer's kinematics. Auto-generated configurations such as PID values, bed meshes, etc are also stored here as in a typical Klipper setup. 
* railcore.cfg - this file defines the printer's hardware configuration by calling [include]s to individual hardware modules.
* user.cfg - the user configuration file is intended for any settings that are machine-specific or user preference. Items such as probe offsets, input shaper configurations, etc should be stored here. In general, changes to default settings should be made as overrides here rather than modifying the base component configuration files.

# File Tree

| Directory | Description |
|-----------|-------------|
| accel     | Accelerometer modules for input shaping |
| extruder  | Extruder modules |
| fan       | Fan modules. Module names prepended with fan function |
| heater    | Heater modules including bed and chamber heaters | 
| hotend    | Hotend modules. Primarily defines maximum safe temperature |
| macro     | Klipper macros |
| mcu       | MCU modules. Modules create pin mappings specific to each board as well as additional mappings to Railcore pin names that are consistent across modules |
| motion    | Motion system modules. Defines axis limits, homing, etc. |
| probe     | Bed probe modules | 
| stepper   | Stepper driver modules. Configures communication method and stepper driver-specific items |
| temp      | Temperature sensor modules |
