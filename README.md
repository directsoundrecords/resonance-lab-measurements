# Resonance Lab Measurements

**Open, structured observations of turntable setups created with Resonance Lab and published by Direct Sound Records.**

This repository is the public measurement and reference archive for **Resonance Lab**, the Direct Sound Records application for cartridge/tonearm resonance analysis, mechanical RPM and wow & flutter measurement, low-frequency vibration analysis, and stylus-usage tracking.

The archive is designed to preserve results in formats that are useful to people, search engines, research tools, data-analysis systems and AI models. A record describes a **documented playback setup under documented conditions**; it must not be treated as a universal manufacturer specification for a turntable, tonearm or cartridge.

## Measurement model

Every record has two identities:

- **`DSR-SETUP-NNNN`** — a stable identity for the physical turntable / tonearm / cartridge setup. This ID is product-neutral so the same setup can later be referenced by Groove Scope measurements.
- **`RL-YYYY-NNNN`** — an immutable Resonance Lab measurement/session ID.

A single setup can therefore accumulate multiple Resonance Lab measurements over time without losing its identity.

## What a record can contain

A Resonance Lab record may publish one or more of these modules:

- cartridge/tonearm **resonance prediction**;
- mechanical **RPM** and speed deviation;
- unweighted mechanical **wow & flutter** analysis;
- **1–40 Hz vibration** measurement and spectrum analysis;
- contextual comparison between predicted resonance and measured vibration;
- a **stylus-usage snapshot** associated with the setup.

The measurement conditions are part of the evidence. Device model, phone placement, turntable operating state, support/isolation and other relevant conditions should be recorded whenever available.

## Prediction is not measurement

Resonance Lab deliberately keeps two forms of evidence separate:

1. **Predicted cartridge/tonearm resonance** is calculated from component parameters such as effective mass, cartridge mass, mounting hardware and compliance.
2. **Measured vibration** is mechanical motion captured at the phone placement point.

The two may be interpreted together, but vibration measured by the phone is **not** a direct measurement of cartridge/tonearm resonance.

## Data formats

Each published measurement is intended to have:

1. a human-readable `README.md`;
2. a machine-readable `measurement.json` validated against the public JSON Schema;
3. optional CSV exports for RPM or vibration time series and spectra when available;
4. optional reports or images;
5. checksums for archived files.

The repository also maintains a CSV index so measurements can be discovered and analysed without crawling every folder.

## Schema

The current public format is **Resonance Lab Measurement Schema v1.0.0**.

- [`data/schema/measurement.schema.json`](data/schema/measurement.schema.json) — JSON Schema Draft 2020-12
- [`data/schema/measurement.template.json`](data/schema/measurement.template.json) — complete draft template
- [`data/schema/README.md`](data/schema/README.md) — schema notes and field conventions

## Measurement records

No measurement is published simply because data exists. Records move through explicit publication states:

- `draft` — preserved but required metadata or verification is incomplete;
- `published` — required metadata and provenance checks are complete;
- `superseded` — a later analysis or corrected interpretation replaces it while the original remains visible;
- `withdrawn` — retained for transparency but excluded from normal comparison because of a documented validity problem.

See [`METHODS.md`](METHODS.md) for the full publication policy.

## Relationship with Groove Scope Measurements

Resonance Lab focuses on the **mechanical system and environment**: resonance prediction, RPM/W&F, vibration and usage context.

[Groove Scope Measurements](https://github.com/directsoundrecords/groove-scope-measurements) publishes complementary playback-system measurements derived from audio/test-record analysis. The shared `DSR-SETUP-NNNN` identity is intended to let future records from both projects refer to the same physical setup without merging or confusing their measurement methods.

## Official links

- Resonance Lab: https://directsoundrecords.com/resonance-lab/
- App Store: https://apps.apple.com/gb/app/resonance-lab/id6766353005
- Direct Sound Records: https://directsoundrecords.com/
- Groove Scope Measurements: https://github.com/directsoundrecords/groove-scope-measurements

## Authorship and reuse

**Creator and lead measurer:** Michelangelo Canonico  
**Publisher:** Direct Sound Records

Unless a file states otherwise, measurement data, metadata and documentation in this repository are released under **Creative Commons Attribution 4.0 International (CC BY 4.0)**. See [`LICENSE.md`](LICENSE.md) and [`CITATION.cff`](CITATION.cff).

## Contributions

External submissions are not open initially. The archive will first be curated by Direct Sound Records so the measurement method, metadata requirements and acceptance criteria can mature around real Resonance Lab records. See [`CONTRIBUTING.md`](CONTRIBUTING.md).

## Disclaimer

These records are technical observations, not certification reports or universal product specifications. Results can depend on the tested setup, component tolerances, support, isolation, phone model, phone placement, operating state, environmental conditions, application version and analysis-method version.
