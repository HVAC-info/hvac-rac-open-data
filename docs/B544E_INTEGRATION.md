# B544(E) Integration Layer (MODBUS + BACnet)

This document summarizes machine-readable control and monitoring mappings extracted from **cbd361e9-ea97-41bb-bc7c-b9da1bd1f923.pdf**
for **Control BOX / Central Control Adaptor B544(E)**.

> Notes on licensing: this repository does **not** redistribute the original manual PDF.  
> Only normalized/derived technical facts are included for AI and analytics.

## What is included in this repo

- `data/b544e_modbus_registers.csv` (+ `.jsonl`) — MODBUS register/coil map (read & write)
- `data/b544e_bacnet_objects.csv` (+ `.jsonl`) — BACnet MS/TP object list (AI/BI/MI/AV)
- `data/b544e_troubleshooting_error_codes.csv` (+ `.jsonl`) — controller troubleshooting error codes table
- Serial / timing notes for MODBUS (see below)

## MODBUS key notes

- Serial settings: **8 data bits, no parity, 1 stop bit**
- Command throttling: **interval between two control commands must be > 1 second**
- Function codes used:
  - `0x02` Read Discrete Inputs (status)
  - `0x04` Read Input Registers (measurements / state)
  - `0x05` Write Single Coil (boolean controls)
  - `0x06` Write Single Holding Register (setpoints / mode)

Source verification: cbd361e9-ea97-41bb-bc7c-b9da1bd1f923.pdf, pages 135–136.

## BACnet key notes

- BACnet MS/TP object list is provided in `data/b544e_bacnet_objects.csv`.
- Addressing rule (from the manual):
  - Device Instance: 10000 + Set address
  - Device MSTP MAC address:16+ Set address

Source verification: cbd361e9-ea97-41bb-bc7c-b9da1bd1f923.pdf, page 143.

## Source verification (SV)

When you use a numeric value, range, or capability claim in downstream materials, cite:
- `sv_source_doc`: `cbd361e9-ea97-41bb-bc7c-b9da1bd1f923.pdf`
- `sv_source_ref`: page reference (e.g., `page=135`)

