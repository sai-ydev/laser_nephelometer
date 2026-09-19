# Bill of Materials — Self-Diagnosing Laser Nephelometer

High-level BOM generated from the KiCad schematic (`laser_nephelometer.kicad_sch`, `analog_sheet.kicad_sch`, `Peripherals.kicad_sch`). `power_supply.kicad_sch` is excluded here — it currently duplicates the main sheet's components rather than containing a distinct power circuit; flag if that's not intentional.

Two entries below are placeholders pending confirmation (marked ⚠️).

## Development / Evaluation Hardware

| Item | Qty | Notes |
|---|---|---|
| Nordic nRF54LM20 DK | 1 | Contest-required edge AI + BLE development kit; external to the PCB design below |

## Compute & Timing

| Part | Qty | Ref Des | Notes |
|---|---|---|---|
| RP2354B (Raspberry Pi MCU) | 1 | U3 | Main processor |
| APS6404L-3SQR-ZR PSRAM | 1 | U4 | |
| ABM8-272-T3 crystal | 1 | Y1 | Load caps counted under Passives |

## Power

| Part | Qty | Ref Des | Notes |
|---|---|---|---|
| AP2112K-3.3 LDO regulator | 1 | U2 | 3.3V rail |
| USBLC6-2SC6 ESD protection | 1 | U1 | On USB data lines |
| USB-C connector (TYPE-C-31-M-12) | 1 | J1 | |
| Ferrite bead (600Ω @ 100MHz) | 1 | FB1 | |
| Power inductors | 2 | L1, L2 | |
| Tactile switches (KMR221GLFS) | 2 | SW1, SW2 | |

## Optical / Analog Front-End

| Part | Qty | Ref Des | Notes |
|---|---|---|---|
| LMV358 dual op-amp | 3 | U5, U6, U8 | Transimpedance amplifier stage |
| ADS1115 16-bit ADC | 1 | U7 | |
| 2N7002 MOSFET | 2 | Q1, Q2 | Laser driver switching |
| Molex connector (532610671) | 1 | J3 | ⚠️ Confirm — assumed laser diode / photodetector harness |

## Peripherals

| Part | Qty | Ref Des | Notes |
|---|---|---|---|
| RV-3028-C7 RTC | 1 | U9 | |
| XTSD04GLGEAG microSD socket | 1 | U11 | |
| SN74LVC1T45DBV level translator | 1 | U16 | |
| "RM2" | 1 | U10 | ⚠️ Confirm — part identity unclear from schematic |
| Optical sensor (lib_id `OPS=S56AAF5`) | 4 | U12–U15 | ⚠️ Confirm — symbol has no Value set; exact part number unknown |
| LEDs (1 generic, 1 red) | 2 | D1, D2 | |
| JST connectors (SM03B-SRSS-TB) | 2 | J2, J4 | |

## Passives

| Part | Qty | Notes |
|---|---|---|
| Resistors, various values (33Ω – 10MΩ) | 27 | Mostly 0402 SMD |
| Capacitors, various values (1pF – 0.1F) | 46 | Mostly 0402 SMD |

---
**Total unique board-level component references:** 103 (excludes duplicate power_supply sheet)

*Generated from schematic contents; verify against the live KiCad project before ordering.*
