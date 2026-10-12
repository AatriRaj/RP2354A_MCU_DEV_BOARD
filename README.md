# RP2354A MCU Development Board

A custom microcontroller-board design built around the **Raspberry Pi RP2354A**, created in KiCad. The schematic includes USB-C connectivity, a 12 MHz crystal, a 3.3 V LDO regulator, boot/reset controls, status indication, and header connections for accessing board signals.

## Project Overview

The goal of this project is to develop a compact RP2354A-based hardware platform for embedded development, prototyping, and experimentation with the RP235x microcontroller family.

## Main Hardware Blocks

- **RP2354A MCU** — the main processing device.
- **USB Type-C connector** — provides the USB connection; the exact power/data behavior should be confirmed against the complete schematic and PCB.
- **12 MHz crystal** — external clock source for the MCU.
- **LD39200PU33R LDO** — 3.3 V regulation.
- **Boot switch** — supports entering the MCU's boot mode when implemented according to the RP2354A documentation.
- **Reset switch** — provides a manual reset control.
- **Status LED** — visual indication for firmware-controlled status or power, depending on its final connection.
- **Passives and decoupling capacitors** — support clock, power, USB, and general circuit operation.
- **Expansion headers** — provide access to selected signals for prototyping and debugging.

## Design Tools

- **Schematic capture:** KiCad
- **Design file supplied:** `RP2354A_MCU.kicad_sch`

## Repository Structure

```text
.
├── README.md
└── RP2354A_MCU.kicad_sch
```

Add the KiCad PCB layout (`.kicad_pcb`), project file (`.kicad_pro`), libraries, fabrication outputs, and firmware source as they become available.

## Opening the Design

1. Install KiCad.
2. Open `RP2354A_MCU.kicad_sch` in **Schematic Editor**.
3. Review the schematic and run **Electrical Rules Checker (ERC)**.
4. Once the PCB layout is available, review footprints and pin mapping, then run **Design Rules Checker (DRC)** before fabrication.

## Before Fabrication

This repository currently documents the supplied schematic, not a verified or production-ready board. Before ordering PCBs:

- Check the RP2354A pin assignments, power rails, decoupling, boot and reset circuitry against the current official datasheet and hardware-design guidance.
- Confirm the USB-C CC resistors, USB data-line routing/protection, and connector pin mapping.
- Verify the LDO input/output voltage limits, capacitor requirements, thermal dissipation, and current budget.
- Confirm the crystal's load-capacitance requirements and the selected capacitor values.
- Check that every required power pin is connected and that unused pins are handled correctly.
- Confirm whether external flash is required for the intended RP2354A configuration and include it if needed.
- Assign and verify all PCB footprints; inspect clearances, copper pours, return paths, and manufacturing constraints.
- Run ERC/DRC and perform a complete schematic-to-PCB connectivity review.

## Current Status

**Hardware schematic in progress.** The supplied file contains the MCU and supporting circuitry. PCB layout, firmware, validation results, and fabrication files are not included in the supplied project file.

## License

No license has been specified yet. Add a license before redistributing or reusing this design.
