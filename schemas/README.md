# Resonance Lab public schemas

The current public archive format is **Schema 2.0.0** using JSON Schema Draft 2020-12.

- `setup.schema.json` validates setup identity and playback-system metadata.
- `measurement.schema.json` validates independent RPM and Vibration observations.

## Publication states

The schemas support three states:

- `draft` — incomplete/private working record; public IDs may be null.
- `submission` — complete Reference Package submitted for archive review; public measurement IDs may still be null because they are assigned centrally by the archive.
- `published` — canonical public archive record; valid public setup and measurement IDs are required.

Public IDs are archive-assigned metadata. Internal UUIDs remain the permanent technical identities used to recognize the same setup or measurement across submissions.

Numerical fields must be interpreted according to each measurement's declared analysis-method version. Historical results are preserved rather than silently recalculated when methods evolve.
