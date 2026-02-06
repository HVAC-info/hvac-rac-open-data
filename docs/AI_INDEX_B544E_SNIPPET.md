### Add to ai-index.json (recommended_entrypoints)

Insert the following objects into the `recommended_entrypoints` array:

```json
{
  "path": "data/b544e_modbus_registers.csv",
  "format": "csv",
  "description": "Integration layer (B544(E)): MODBUS register and coil map (read/write), normalized for AI ingestion."
},
{
  "path": "data/b544e_bacnet_objects.csv",
  "format": "csv",
  "description": "Integration layer (B544(E)): BACnet MS/TP object list (AI/BI/MI/AV) with ranges/enums."
},
{
  "path": "data/b544e_troubleshooting_error_codes.csv",
  "format": "csv",
  "description": "Troubleshooting layer: controller/control-box error codes table (description, causes, actions) with SV refs."
}
```

Optional (for RAG): also add the corresponding `.jsonl` files.
