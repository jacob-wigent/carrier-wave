![Carrier-Wave](./assets/title-logo-dark.png#gh-dark-mode-only)
![Carrier-Wave](./assets/title-logo-light.png#gh-light-mode-only)

---

A portable, USB-C powered function generator currently under development. This project aims to combine DDS-based waveform generation with low-noise analog design in a compact and affordable form factor.

### Navigate

| |  |  |
|-----------|---------|---------|
| **[Hardware](./hardware/README.md)** | Circuit design and PCB layout | KiCad design files, simulations |
| **[Firmware](./firmware/README.md)** | Microcontroller implementation | STM32 code, CubeMX configuration |
| **[Software](./software/README.md)** | Desktop control interface | JavaFX GUI application code |

## Target Capabilities

- **Frequency:** up to 25 MHz sine waves
- **Waveforms:** Sine, square, triangle (via DDS), and arbitrary[†](#footnotes) (via MCU DAC)
- **Output amplitude:**
  - 20 Vpp (±10 V) into high-impedance load  
  - 10 Vpp (±5 V) into 50 Ω load
  - Vpp/2 DC offset
- **Output resolutions:**
  - Frequency: <0.5 Hz (28-bit frequency tuning word at 75-100Mhz)
  - Amplitude: ~5mV (dependent on analog design)
  - Offset: ~5mV (dependent on analog design)
- **Output impedance:** ~50 Ω (for matched loads)
- **Signal purity:** Low harmonic distortion, minimal spurs from DDS

## Roadmap

- [x] System architecture defined  
- [ ] Component selection finalized
- [ ] Analog simulation
- [ ] Signal quality estimated
- [ ] Schematic capture
- [ ] PCB layout  
- [ ] Firmware development
- [ ] Software development

See the [open issues](https://github.com/jacob-wigent/carrier-wave/issues) for a full list of proposed features (and known issues).

## Tools
- **Hardware Design:** KiCad 10.0 for schematic capture and PCB layout
- **Simulation:** LTSpice / MATLAB for analog characterization
- **Firmware:** STM32CubeIDE or PlatformIO (planned)
- **Software:** JavaFX for desktop interface (planned)

## License

This project is released under the **CERN Open Hardware Licence Version 2 – Strongly Reciprocal (CERN-OHL-S v2)**.  

You are free to use, modify, and distribute the hardware and design files, provided that derivative works are also shared under the same license.  

For full license details, see the [LICENSE](LICENSE) file.

#### Footnotes:
- † Abitrary waveform generation is a potential feature using one of the STM32G4s built-in DACs. This output would be limited to lower frequencies (under 1Mhz) and waveform storage would be limited due to memory constraints.