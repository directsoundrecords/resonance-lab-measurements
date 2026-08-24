# Resonance Lab Measurements

**Public, setup-centric technical observations created with Resonance Lab and curated by Direct Sound Records.**

This repository preserves turntable playback setups and their Resonance Lab measurement history in human-readable and machine-readable formats. The archive is designed for reproducibility, long-term comparison, search, research and AI-assisted analysis.

## Archive model

The archive is **setup-centric**:

- `DSR-SETUP-NNNN` identifies a documented playback setup.
- `RL-YYYY-NNNN` identifies one immutable Resonance Lab measurement/observation.
- One setup may contain zero, one or many measurements of each supported type.
- New measurements are appended over time; historical measurements are not silently rewritten.

A change in operating conditions does not create a new setup. A material change to the playback system itself — for example a different turntable, tonearm or cartridge — should normally receive a new setup identity.

### Public ID assignment

Resonance Lab generates permanent internal UUIDs for setups and measurements. Contributors do **not** need to choose public archive numbers. Submission packages are matched by UUID and the Direct Sound Records archive assigns public IDs centrally when records are accepted. This prevents collisions across users and devices and lets repeat submissions of the same measurement be recognized reliably.

The current allocator uses six-digit measurement sequences, for example `RL-2026-000001`.

## Repository structure

```text
schemas/
  setup.schema.json
  measurement.schema.json

data/
  setups.csv
  measurements.csv

setups/
  DSR-SETUP-0001/
    README.md
    setup.json
    measurements/
      RL-YYYY-NNNNNN/
        README.md
        measurement.json
        ...
```

The repository keeps the current canonical schemas at the top level. Resonance Lab Reference Package ZIP exports may additionally embed schema copies, manifests and checksums so the exported package remains self-contained; repository records are normalized to the canonical repository structure above.

## Current schema

The current public archive format is **Schema 2.0.0** and uses JSON Schema Draft 2020-12.

- [`schemas/setup.schema.json`](schemas/setup.schema.json)
- [`schemas/measurement.schema.json`](schemas/measurement.schema.json)
- [`schemas/README.md`](schemas/README.md)

The schema supports `draft`, `submission` and `published` states. Public measurement IDs may remain unassigned in a submission package and become mandatory only for the canonical published record.

## Measurement types

Resonance Lab currently archives independent observations including:

- cartridge/tonearm resonance prediction context;
- mechanical RPM and unweighted wow & flutter observations;
- 1–40 Hz mechanical vibration observations;
- contextual Resonance × Vibration interpretation;
- stylus-usage snapshots captured at measurement time where available.

RPM and Vibration sessions remain separate measurements. Vibration-specific conditions such as support, isolation, floor, phone placement, motor/platter/stylus/speaker state belong to the individual Vibration observation. RPM uses only the smaller RPM Test State relevant to that session.

## Prediction is not measurement

Predicted cartridge/tonearm resonance and phone-measured vibration are different evidence types. Resonance Lab may compare their frequency context, but vibration measured at the phone location is **not** a direct measurement of stylus/cantilever or cartridge/tonearm resonance.

Dominant local spectral peaks are also distinct from stronger significant/confident-peak classifications. A reported local peak does not by itself establish its mechanical cause.

## Method versioning and historical integrity

Every measurement preserves the application, device and analysis-method provenance available at capture time. Analysis improvements receive explicit method versions. Historical observations retain the values and method version with which they were created.

Consumers should interpret numerical fields according to the method version stored with each measurement.

## Public setups

- [`DSR-SETUP-0001`](setups/DSR-SETUP-0001/) — Rega P3 / Rega RB330 / Audio-Technica AT-OC9XML — 3 published observations (2 RPM, 1 Vibration).
- [`DSR-SETUP-0002`](setups/DSR-SETUP-0002/) — Technics SL-1410 mk2 / AMG 12J2 / Ortofon 2M Blue — 6 published observations (2 RPM, 4 Vibration).

New measurements can be appended later without changing the setup ID.

## Data indexes

- [`data/setups.csv`](data/setups.csv) — one row per public setup.
- [`data/measurements.csv`](data/measurements.csv) — one row per public Resonance Lab observation, including internal measurement UUID and source-submission provenance for duplicate detection and archive traceability.

The indexes are discovery aids. The JSON record remains the canonical machine-readable source for each setup or measurement.

## Attribution

Measurement authorship belongs to each individual measurement. Direct Sound Records is the archive publisher and Resonance Lab software developer; it is not automatically the measurement author for third-party submissions.

Anonymous attribution is supported when explicitly selected. Private account data, precise GPS location and device-owner information are not part of the public archive.

## Reuse

Unless a record states otherwise, public measurement data and documentation are released under **Creative Commons Attribution 4.0 International (CC BY 4.0)**. See [`LICENSE.md`](LICENSE.md) and [`CITATION.cff`](CITATION.cff).

## Official links

- Resonance Lab: https://directsoundrecords.com/resonance-lab/
- Direct Sound Records: https://directsoundrecords.com/
- App Store: https://apps.apple.com/gb/app/resonance-lab/id6766353005
- Groove Scope Measurements: https://github.com/directsoundrecords/groove-scope-measurements
