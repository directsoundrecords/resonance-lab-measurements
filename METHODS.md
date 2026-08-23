# Publication and measurement policy

## Purpose

This repository is a curated archive of Resonance Lab setups and observations. It preserves what was measured, the conditions and provenance available at the time, and the analysis-method version used to produce the result.

## Setup and measurement identity

A public setup receives a stable `DSR-SETUP-NNNN` identifier. Each public Resonance Lab observation receives its own immutable `RL-YYYY-NNNN` identifier.

The setup is the long-lived playback-system identity. Measurements are dated observations appended beneath that setup. Repeating the same test, changing phone position, turning speakers on or off, or measuring months later does not replace an earlier observation.

A material change to the playback system itself — for example a different turntable, tonearm or cartridge — should normally create a new setup identity.

## Measurement timestamps

Measurement timestamps describe when the observation occurred. Package-generation time is separate and must not replace the measurement timestamp.

## Measurement context

Vibration context belongs to each individual Vibration measurement because support, isolation, floor, phone placement and operating state can vary between observations.

RPM measurements use a smaller RPM Test State containing only information relevant to that session, such as target speed and record/stylus state.

Mutable setup parameters that are relevant to interpretation may also be snapshotted into the measurement so later setup edits do not change the historical meaning of the observation.

## Provenance and method versions

New measurements preserve available app version/build, device/OS, timezone and relevant analysis-method versions at measurement time. Historical observations are not backfilled with present-day device or setup values.

An analysis change that changes numerical meaning receives a new method version. Previously published measurements retain their original values and method version.

## RPM and wow & flutter

RPM/W&F values are mechanical motion-sensor observations. They must not be described as standards-certified weighted wow & flutter unless a future method explicitly implements and validates a named standard. Current exported weighting should be interpreted from the stored method and `weighting` field.

## Vibration

Vibration observations describe mechanical motion at the phone placement point over the declared analysis range. Current records use a 1–40 Hz range with the following non-overlapping bands:

- `1 <= f < 8 Hz`
- `8 <= f < 20 Hz`
- `20 <= f <= 40 Hz`

Consumers must interpret band RMS and energy values according to the stored Vibration analysis-method version. Newer Parseval-normalized methods and preserved legacy methods may have different estimator semantics.

## Dominant peaks and confidence

`dominant_peaks` represent stored local spectral maxima selected by the declared Dominant Peak method. Their presence is separate from stronger significant/confident-peak classification.

A dominant local peak does not by itself establish cartridge/tonearm resonance, acoustic feedback, motor vibration, structural resonance or another physical cause.

## Resonance × Vibration combined analysis

Combined analysis compares a predicted cartridge/tonearm resonance region with measured mechanical vibration context. It distinguishes resonance position, frequency coverage, local peaks, nearby features and confidence.

Phone vibration is not a direct measurement of stylus/cantilever or cartridge/tonearm resonance. Combined analysis must use contextual language and avoid causal claims unsupported by the measurement.

## Authorship and submission

Measurement authorship is stored per measurement. The submitter may differ from the measurement author. Direct Sound Records is the archive publisher.

Named, affiliated and anonymous contribution modes may be represented when explicitly selected. Public attribution must never be inferred from Apple account information or device-owner data.

## Publication states

The schema supports explicit publication state. Public records require valid public IDs. Draft records may remain without public IDs while they are being reviewed.

Published numerical evidence should not be silently changed. Corrections or later analyses should preserve the historical record and document what changed.

## Missing information

Missing data is not automatically an error. Use explicit states such as `not_recorded`, `not_available`, `not_applicable` or `not_confirmed` according to their documented meaning. Never invent metadata merely to make a record appear complete.

## Integrity

Self-contained setup packages may include manifests and SHA-256 checksums. Structured JSON is the canonical archive representation; CSV time series/spectra, reports and charts are supporting evidence or derived presentation artifacts.
