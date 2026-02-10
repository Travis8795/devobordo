# devobordo

devobordo is a custom RP2040 development board designed from scratch in KiCad.

The goal of this project was to deeply understand the RP2040 architecture, power design, PCB layout, and manufacturability constraints (JLCPCB).

This board provides a minimal but fully functional RP2040 platform with clean power routing, proper decoupling, USB interface, and full GPIO breakout for experimentation.


| front | back |
| :---: | :---: |
| <img width="1336" height="665" alt="Screenshot 2026-02-10 220047" src="https://github.com/user-attachments/assets/0df9a42c-9b21-4f85-a454-f1cc8e0d16d5" /> | <img width="540" height="792" alt="Screenshot 2026-02-10 220109" src="https://github.com/user-attachments/assets/430513d4-d5c3-4eb0-856e-62dfe45bc653" /> |

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

---

| front layer | back layer | schema |
| :---: | :---: | :---: |
| <img width="228" height="553" alt="Screenshot 2026-02-10 220607" src="https://github.com/user-attachments/assets/103a7305-779d-4cf1-8ccb-f85d48699586" /> | <img width="231" height="550" alt="Screenshot 2026-02-10 220547" src="https://github.com/user-attachments/assets/5608bde4-f5d5-47f2-ad24-7cdf741b6f25" /> | <img width="992" height="679" alt="Screenshot 2026-02-10 220213" src="https://github.com/user-attachments/assets/47d9b6cc-1522-4254-8ea5-a852176c2aef" /> |
