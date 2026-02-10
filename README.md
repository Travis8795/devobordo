# devobordo

devobordo is a custom RP2040 development board designed from scratch in KiCad.

The goal of this project was to deeply understand the RP2040 architecture, power design, PCB layout, and manufacturability constraints (JLCPCB).

This board provides a minimal but fully functional RP2040 platform with clean power routing, proper decoupling, USB interface, and full GPIO breakout for experimentation.


## Features

- RP2040 (Dual-core ARM Cortex-M0+ @ 133MHz)
- USB-C and battery power input
- MCP1700 3.3V linear regulator
- External QSPI Flash
- 12 MHz crystal oscillator
- SWD programming/debug header
- Dual LED indicators:
  - Power LED (3V3)
  - GPIO25 activity LED
- Full GPIO breakout headers
- 2-layer PCB optimized for low impedance power routing


## Power Architecture

- USB 5V input
- Reverse protection diode
- MCP1700 3.3V LDO regulator
- Wide 3V3 power backbone (low impedance design)
- Ground plane with via stitching
- Proper decoupling for:
  - 3V3 rail
  - 1V1 core regulator
  - QSPI flash
  - Crystal oscillator


## PCB Design Goals

- Clean ground return paths
- Short and wide 3V3 rails
- Correct USB D+ / D− routing
- Thermal relief tuning
- DRC-clean for JLCPCB production
- Use of JLC basic parts where possible

## Designed With

- KiCad 9
- JLCPCB assembly constraints
- RP2040 datasheet reference design
- Blueprint Hackclub devboard guide


## Manufacturing

- 2-layer PCB
- 1oz copper
- JLCPCB assembly
- Standard component footprints (0603, 0402)


## What I Learned

- RP2040 power domain separation (3V3 vs 1V1)
- Decoupling capacitor placement strategy
- Thermal relief tuning
- USB differential routing basics
- DRC debugging and constraint fixing
- Designing for automated assembly
