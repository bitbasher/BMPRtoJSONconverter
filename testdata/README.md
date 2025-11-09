# Test Data

This folder contains test BMPR files and their JSON conversions.

## Files

- **bank.bmpr** - Sample banking website mockup (schema 2.0)
- **PreferencesProject.bmpr** - Preferences dialog mockup (schema 2.0)
- **bmpr-schema.json** - JSON Schema for validating converted BMPR JSON output

## Validating JSON Output

The JSON schema can be used to validate that the converter output matches the expected structure.

### Using ajv-cli

Install ajv-cli globally:
```bash
npm install -g ajv-cli
```

Validate a JSON file:
```bash
ajv validate -s bmpr-schema.json -d bank.json
ajv validate -s bmpr-schema.json -d PreferencesProject.json
```

### Using check-jsonschema (Python)

Install check-jsonschema:
```bash
pip install check-jsonschema
```

Validate a JSON file:
```bash
check-jsonschema --schemafile bmpr-schema.json bank.json
check-jsonschema --schemafile bmpr-schema.json PreferencesProject.json
```

## Converting BMPR Files

To convert a BMPR file to JSON:

```bash
# From the repository root
./JsonConverterBmpr/bin/Release/JsonConverterBmpr.exe testdata/bank.bmpr testdata/bank.json -f

# Or output to stdout
./JsonConverterBmpr/bin/Release/JsonConverterBmpr.exe testdata/bank.bmpr
```

## Schema Information

The JSON schema defines the structure of the converted output including:
- Project metadata (info)
- Mockups with controls
- Branches (alternate versions)
- Assets and symbol libraries
- Thumbnails

The schema supports both BMPR schema version 1.x and 2.0 formats.
