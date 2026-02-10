# devobordo

devobordo is a custom RP2040 development board designed from scratch in KiCad.

The goal of this project was try and work on the RP2040 architecture, power design, PCB layout, and manufacturability constraints (JLCPCB).

This board provides a minimal but fully functional RP2040 platform with clean power routing, proper decoupling, USB interface, full GPIO breakout for experimentation, and battery capability.


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
- DRC debugging
- Dealing with ground isolated islands

---


| front layer | back layer | schema |
| :---: | :---: | :---: |
| <img width="228" height="553" alt="Screenshot 2026-02-10 220607" src="https://github.com/user-attachments/assets/103a7305-779d-4cf1-8ccb-f85d48699586" /> | <img width="231" height="550" alt="Screenshot 2026-02-10 220547" src="https://github.com/user-attachments/assets/5608bde4-f5d5-47f2-ad24-7cdf741b6f25" /> | <img width="992" height="679" alt="Screenshot 2026-02-10 220213" src="https://github.com/user-attachments/assets/47d9b6cc-1522-4254-8ea5-a852176c2aef" /> |

---
## BOM table

| Description       | Value        | Footprint | LCSC Part # | Quantity | Notes             |
| ----------------- | ------------ | --------- | ----------- | -------- | ----------------- |
| Microcontroller   | RP2040       | QFN-56    | C2040       | 1        | Main MCU          |
| QSPI Flash        | W25Q16JV     | SOIC-8    | C97521      | 1        | External flash    |
| LDO Regulator     | MCP1700-3302 | SOT-23    | C62354      | 1        | 3.3V regulator    |
| Crystal           | 12MHz        | 3225      | C9002       | 1        | Main clock        |
| LED               | Red 0603     | 0603      | C2286       | 2        | Power indicator, and GPIO25|
| Resistor          | 1kΩ          | 0402      | C21190      | 2        | LED current limit |
| Resistor          | 27Ω         | 0402      | C21190      | 2        | USB D+/D- |
| Resistor          | 5.1KΩ         | 0402      | C21190      | 2        | CC pull down |
| Ceramic Capacitor | 100nF        | 0402      | C14663      | 11        | Decoupling        |
| Ceramic Capacitor | 10uF         | 0603      | C19702      | 2        | Bulk filtering    |
| Ceramic Capacitor | 1uF          | 0402      | C15849      | 2        | Core regulator    |
| Ceramic Capacitor | 33pF          | 0402      | C1562      | 2        | crystal filtering    |
| Push Button | SW_Push | SW_Push_SPST_NO_Alps_SKRK  | C341730      | 1        | Bootloder    |
| Diod | 1N4148WT | D_SOD-123  | C78089      | 2       | Reverse protection    |
| USB_C receptacle | USB_C_Receptacle_USB2.0_14P | USB_C_Receptacle_HRO_TYPE-C-31-M-12  | C165948      | 1        | USB connection    |



