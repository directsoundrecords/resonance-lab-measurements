# Changelog

## 2026-08-24 — Second public setup

- Added `DSR-SETUP-0002`: Technics SL-1410 mk2 / AMG 12J2 / Ortofon 2M Blue.
- Published six Resonance Lab observations from submission `6143697D-7CAC-48D1-AB8F-A2AA3ECBFD93`:
  - `RL-2026-000004` — RPM / W&F, record not recorded, stylus not tracking.
  - `RL-2026-000005` — RPM / W&F, record present, stylus tracking.
  - `RL-2026-000006` — Vibration, context not recorded.
  - `RL-2026-000007` — Vibration, motor off / platter stationary / speakers inactive / phone on turntable top plate.
  - `RL-2026-000008` — Vibration, motor off / platter stationary / speakers active / phone on plinth.
  - `RL-2026-000009` — Vibration, motor off / platter stationary / speakers active / phone on platter.
- Preserved the source-package SHA-256 in `data/measurements.csv` for archive traceability.

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
