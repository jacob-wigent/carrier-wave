# Hardware

Hardware design for the Carrier-Wave function generator.

> 🚧 Under development

## Architecture Overview

The Carrier-Wave hardware combines DDS-based digital waveform generation with a precision analog stage and low-noise power system.

**MCU:** STM32G0 or STM32G4  
- Controls DDS over SPI
- Handles user interface and system logic

**DDS:** AD9834 *(potential overclocking to ~100 MHz MCLK)[†](#footnotes)
- Generates base waveform (sine, triangle, square)  
- Output filtered and amplified by analog stage

## Power System

- **Dual-rail boost converter (TPS65131)**  
  - Generates positive and negative rails for analog stage  

- **Ultra-low-noise LDOs (LT3045 & LT3094)**  
  - Post-regulation for clean analog supply rails  
  - Minimizes ripple and switching noise from boost stage

## Analog Stage

- **Transimpedance Pre-Amplifier**  
  - Converts DDS current output to voltage  
  - Sets initial signal amplitude before filtering

- **Reconstruction Filter (High-Order Butterworth)**  
  - Removes DDS images and high-frequency components  
  - Designed for flat passband and minimal ripple 

- **Output Amplifier**
  - Scales signal to target voltage range (up to ±10 V)  
  - Drives both high-impedance and 50Ω loads 

## User Interface

- 128×64 OLED display (SSD1309)  
- Rotary encoder for input  
- USB-C connector 
- BNC connector

## Design Considerations

- **Noise Isolation:** Separation of digital, power, and analog sections to minimize interference
- **Signal Integrity:** Short, controlled traces and proper impedance for high-frequency paths  
- **Power Quality:** Multi-stage regulation (boost + LDOs + local decoupling) for clean analog rails
- **Thermal Management:** Adequate copper area and layout to dissipate heat from regulators, amps, or DDS

## Notes

- DDS clocking, filtering, and amplifier bandwidth will ultimately define achievable signal quality at higher frequencies.
- Analog performance will be validated through simulation and measurement during later development stages.

#### Footnotes:
- † Overclocking the AD9834 may increase power dissipation and degrade spectral performance due to internal timing violations, and is not guaranteed by the manufacturer. [ADI](https://www.analog.com/en/resources/product-faqs/ad9834.html)