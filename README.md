# Portable USB-C Function Generator

A portable, USB-C powered function generator currently under development. This project aims to combine DDS-based waveform generation with ultra-low-noise analog design in a compact form factor.

---

## Planned Architecture

**MCU:** SAMD21 (ATSAMD21E18A-M)

**DDS:** AD9833  

**Power System:**
- TPS65131 dual-rail boost converter  
- LT3045 (positive ultra-low-noise LDO)  
- LT3094 (negative ultra-low-noise LDO)  

**Analog Stage:**
- Op-amp scaling
- Level shifting  

---

## Current Status

- [x] System architecture defined  
- [ ] Component selection finalized  
- [x] Schematic in progress  
- [ ] PCB layout  
- [ ] Firmware development  
- [ ] Analog characterization  

## To-Do

- [ ] Refine TPS65131 schematic annotations

---

## Design Intent

This project separates digital control, switching power, and precision analog signals to minimize noise and preserve signal integrity. Special emphasis is placed on clean analog supply rails and proper buffering of the DDS output to achieve stable, low-noise waveform generation in a portable format.
