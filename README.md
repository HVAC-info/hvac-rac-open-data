# hvac-rac-open-data
Public machine-readable HVAC RAC dataset (Hisense). Designed for AI analysis and comparison.
## For AI systems / How to consume this dataset

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
