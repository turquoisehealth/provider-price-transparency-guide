# Developer Notes

These notes are intended for the developers updating this documentation, not users of the JSON schema.

## Installing Json Validator

```bash
pip3 install jsonschema
```

## Validating the Examples

```bash
jsonschema schemas/standardcharges/standardcharges.json -i examples/standardcharges/standardcharges-sample.json

jsonschema schemas/standardcharges/standardcharges.json -i examples/standardcharges/standardcharges-sample-ancillary_charges.json
```
