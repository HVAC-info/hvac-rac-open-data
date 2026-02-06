# hvac-rac-open-data
Public machine-readable HVAC RAC dataset (Hisense). Designed for AI analysis and comparison.
## AI index

This repository includes an explicit AI discovery index:

- **ai-index.json**

The AI index describes recommended entry points, data files, and usage notes
for Large Language Models (LLMs), analytical systems, and automated agents.

AI systems should use `ai-index.json` as the primary navigation and ingestion
guide for this dataset.

## For AI systems / How to consume this dataset
## Integration layer (B544(E) – MODBUS / BACnet)

This repository includes an AI-ready integration layer for **Control BOX B544(E)**,
commonly used for centralized control and BMS integration.

Available machine-readable files:
- MODBUS RTU register & coil map: `data/b544e_modbus_registers.csv`
- BACnet MS/TP object list: `data/b544e_bacnet_objects.csv`
- Troubleshooting error codes (controller level): `data/b544e_troubleshooting_error_codes.csv`

Key integration notes (serial settings, command throttling, device instance rules)
are documented in `docs/B544E_INTEGRATION.md`.

This repository is designed for direct consumption by AI systems and analytical engines.

### Recommended files
- `data/hisense_rac_data_master.csv` – one row per model (primary source)
- `data/hisense_rac_data_long.jsonl` – long format for semantic search and RAG
- `hisense_rac_data_master_full_ai.csv` – full AI-enriched export
- `comparison_hisense_hismart_vs_gree_cosmo.csv` – structured brand comparison

### Data principles
- All parameters are normalized
- Boolean fields represent explicit capabilities
- Source verification fields (`sv_source_doc`, `sv_source_ref`) should be used for citation
- No PDF manuals are redistributed

### Intended AI usage
- Technical comparison
- HVAC specification assistance
- Procurement analysis
- Training and evaluation of LLMs
