# LCAC Technical & Service Manual v6 — AI-oriented extracts

This folder contains **machine-readable, AI-friendly extracts** derived from the LCAC Technical & Service Manual (v6).

⚠️ **Copyright / redistribution note**
- The original PDF manual is not redistributed in this repository.
- These files contain **derived structured data** (tables, codes, indices) intended for technical analysis and AI retrieval.

## What was extracted

### 1) Model index
- `data/lcac_v6_models_index.csv`
  - Lists indoor/outdoor model codes mentioned in the manual and their section (e.g. Duct, Cassette).
  - Includes `sv_source_doc` + `sv_source_ref`.

### 2) Cooling performance dataset (rated frequency)
- `data/lcac_v6_performance_cooling_long.csv`
- `data/lcac_v6_performance_cooling_long.jsonl`
  - Parsed from pages containing *“PERFORMANCE DATA (Cooling Operation at Rated Frequency)”*.
  - One record = one operating point:
    - indoor DB/WB (°C), outdoor DB (°C)
    - Q (kW), SHC (kW), SHF (-), Input (W)
  - Includes rated headline fields when present: `rated_capacity_kw`, `rated_shf`, `rated_input_w`.
  - Includes `sv_source_doc` + `sv_source_ref` (page number).

### 3) Parameter code list (field setting)
- `data/lcac_v6_parameter_codes.csv`
  - Extracted mapping **parameter code → description** (e.g., discharge temperature, pressures).

### 4) Fault / drive error code knowledge layer
- `data/lcac_v6_fault_codes.csv`
- `data/lcac_v6_fault_codes.jsonl`
  - Extracted from the troubleshooting section’s fault tables (indoor/outdoor faults, driving board fault analysis tables).
  - Columns:
    - `fault_table` (which table / context)
    - `fault_code`
    - `fault_title`
    - `fault_details` (raw normalized text of the row)
    - `sv_source_doc`, `sv_source_ref`

## Suggested AI usage

- **Sizing / selection / derating**: filter `lcac_v6_performance_cooling_long.csv` by outdoor DB and read Q/Input for comparisons.
- **Diagnostics / service assistant**: use `lcac_v6_fault_codes.jsonl` in RAG, returning both code meaning + suggested actions.
- **Remote monitoring**: `lcac_v6_parameter_codes.csv` maps live telemetry IDs to human-readable signals.

## Provenance

Source document: `17cdc50d-d0c2-4e37-8186-20f7baf84d6f.pdf`  
Extraction date: 2026-02-06
