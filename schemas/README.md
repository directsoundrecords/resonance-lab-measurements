# Resonance Lab public schemas

The current public format is **2.0.0** and uses JSON Schema Draft 2020-12.

- `setup.schema.json` validates the stable setup-level record.
- `measurement.schema.json` validates independent Resonance Lab observations and applies type-specific rules for RPM and Vibration records.

Draft records may omit public IDs according to schema rules. Published records require valid public setup and measurement IDs.

Consumers should use the `analysis_method_version` and related method-version fields stored in each measurement when interpreting numerical results. Schema descriptions are intentionally method-neutral where historical and current analysis versions have different semantics.
