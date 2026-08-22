# Publication and measurement policy

## Purpose

Resonance Lab Measurements is a curated public archive created by Michelangelo Canonico and Direct Sound Records. Its purpose is to document real turntable setups and mechanical observations in a transparent and reusable form, not to manufacture league tables from incomparable systems.

## Record identity

Every physical setup receives a stable `DSR-SETUP-NNNN` identifier. Every Resonance Lab session receives an immutable `RL-YYYY-NNNN` measurement identifier. Correcting metadata does not change either identity; corrections create a new `record_version` and should be documented in the changelog.

## Publication status

- `draft`: data preserved, but required metadata or verification is incomplete.
- `published`: required metadata and provenance checks are complete.
- `superseded`: a later analysis or corrected record replaces the interpretation; the old record remains available.
- `withdrawn`: retained for transparency but excluded from normal comparison because of a documented validity problem.

## Software and method changes

Every future record should store both:

- `application_version`: the user-facing Resonance Lab release;
- `analysis_method_version`: the internal version of the relevant calculation or measurement algorithm.

A later app version must not silently rewrite a historical result. Reanalysis should create a new record version or a new measurement while preserving the original values and provenance.

## Minimum metadata for a published record

A final public record should identify, where relevant:

- turntable, tonearm and cartridge/stylus;
- effective mass, cartridge mass, mounting mass and compliance used for resonance prediction;
- support type and isolation devices;
- phone model and operating-system version;
- exact phone placement and orientation;
- motor/platter/record/stylus/speaker operating state;
- target RPM and measurement duration;
- Resonance Lab application version and analysis-method version;
- measurement date, location label and repeat number.

When information is genuinely unavailable, use an explicit state such as `not_recorded`. Never infer a model or setting merely because it seems likely.

## RPM and wow & flutter

RPM/W&F results are mechanical motion-sensor observations. Schema v1 records average RPM, target deviation, peak deviation, speed standard deviation and unweighted wow/flutter metrics using the frequency bands stated in the record. These values should not be presented as standards-certified weighted wow & flutter unless a future method explicitly implements and validates a named standard.

## Vibration

Vibration results describe mechanical motion at the phone placement point. For meaningful comparison, phone placement, orientation and operating conditions should be kept as consistent as possible. Schema v1 uses a 1–40 Hz analysis range with 1–8 Hz, 8–20 Hz and 20–40 Hz summary bands.

## Prediction versus measurement

Cartridge/tonearm resonance prediction and phone vibration are different evidence types. A resonance prediction is calculated from component parameters. A vibration measurement captures mechanical motion at the phone location. A combined analysis may compare their frequency context but must never claim that the phone directly measured cartridge/tonearm resonance.

## Repetition and interpretation

Single-session measurements should be treated as observations. Variable conditions should be repeated before mechanical changes or product comparisons are made. Records should state when repeat measurement is recommended.

## Raw sensor data

Raw sensor time series are optional. Derived data, metadata, spectra, visualisations and reports are sufficient for an initial public record when provenance is documented. If raw time-series or spectrum CSV files are published, they should be referenced from `measurement.json` and included in checksums.

## Corrections

Corrections should be made through a documented commit naming the measurement ID and reason, for example:

`Correct phone placement metadata for RL-2026-0001`

Numerical values should only be changed when the source was transcribed incorrectly. If the algorithm itself changes, preserve the historical result and publish a new analysis or record version.
