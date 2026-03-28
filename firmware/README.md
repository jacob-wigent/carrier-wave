# Firmware

Firmware for the Carrier-Wave function generator.

> 🚧 Coming soon — firmware development has not yet begun.

The firmware is responsible for real-time control of the function generator hardware. Running on a microcontroller, it will coordinate waveform generation, user interaction, and system management.

Core responsibilities include:

- Configuring and controlling the DDS via SPI
- Managing waveform parameters (frequency, amplitude, offset)
- Driving the user interface (buttons, encoders, display)
- Handling system state and presets
- Providing communication with external software (USB / serial)

## Planned Features

- DDS control driver (SPI-based)
- Parameter control (frequency, phase, waveform type)
- Menu-driven UI
- Display driver integration
- USB or UART communication interface
- Calibration routines

## Notes

More details will be added as development begins.
