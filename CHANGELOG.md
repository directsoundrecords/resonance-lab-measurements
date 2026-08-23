# Changelog

## 2026-08-23 — Setup-centric public archive v2

- Adopted public Schema `2.0.0`.
- Made the archive setup-centric: one stable `DSR-SETUP-NNNN` with zero-to-many independent `RL-YYYY-NNNN` observations.
- Added separate setup and measurement schemas.
- Added per-measurement timestamp, provenance, attribution and immutable setup snapshots.
- Separated RPM Test State from Vibration Context.
- Documented method-versioned Vibration RMS, Dominant Peaks and Combined Resonance × Vibration interpretation.
- Added setup and measurement indexes.
- Added first public setup identity: `DSR-SETUP-0001`.
- Added archive-assigned public-ID workflow for UUID-based submission packages.
- Published the first three Resonance Lab observations under `DSR-SETUP-0001`:
  - `RL-2026-000001` — RPM / W&F.
  - `RL-2026-000002` — RPM / W&F.
  - `RL-2026-000003` — Vibration.
