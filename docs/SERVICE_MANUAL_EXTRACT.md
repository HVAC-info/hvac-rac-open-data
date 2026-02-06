# Service Manual extract (machine-readable)

This folder contains structured extracts from `Service Manual RAC v2.2.docx` for AI/analytics use.

## Files
- `service_manual_specs_wide.csv` — one row per model, columns = parameters (as slugs).
- `service_manual_specs_long.jsonl` — long format (one record per model+parameter) with `sv_source_doc` and `sv_source_ref`.

## Source referencing
- `sv_source_doc`: source document name
- `sv_source_ref`: internal pointer like `table_6` (table index inside the DOCX)

## Note
Some parts of the manual are not stored as native tables (e.g., images or diagrams). If you need **error/fault code tables** and they are embedded as images, they may require manual extraction or OCR.
