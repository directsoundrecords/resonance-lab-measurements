# Resonance Lab Measurement Schema v1.0

This folder defines the first public-data format for **DSR Resonance Lab Measurements**.

The objective is to make each published observation understandable to humans, search engines, research tools and AI systems while preserving the distinction between setup metadata, prediction, physical measurement, contextual analysis and maintenance context.

## Two identities

Every public record has:

- `setup_id` — `DSR-SETUP-NNNN`: stable identity for the physical turntable/tonearm/cartridge setup, reusable across Resonance Lab and Groove Scope datasets.
- `measurement_id` — `RL-YYYY-NNNN`: immutable identity for one Resonance Lab observation/session.

A setup may accumulate multiple measurements over time without losing its identity.

## Unknown values

Do not guess missing metadata. Use one of:

- `not_recorded`
- `not_applicable`
- `not_available`
- `not_confirmed`

## Measurement modules

A record may contain one or more of:

- `resonance_prediction`
- `rpm`
- `wow_flutter`
- `vibration`
- `combined_analysis`
- `stylus_usage_snapshot`

A record does not need every module.

## Scientific distinction

`resonance_prediction` and `vibration` are not the same measurement. The resonance model predicts the natural frequency of the cartridge/tonearm mechanical system from component parameters. The vibration module measures mechanical motion at the phone placement point. `combined_analysis` may interpret their relationship but must never describe the vibration sensor as directly measuring cartridge/tonearm resonance.

## Units fixed in schema v1

- mass: grams (`g`)
- cartridge compliance: `µm/mN`
- frequency: hertz (`Hz`)
- rotational speed: revolutions per minute (`RPM`)
- speed/wow/flutter variation: percent (`%`)
- vibration acceleration: milligravity (`mg`)
- duration: seconds (`s`)

## Versioning

- `schema_version`: data-format version, initially `1.0.0`
- `record_version`: version of an individual public record
- `software.application_version`: user-facing Resonance Lab release
- `software.analysis_method_version`: algorithm/method version used to produce the result

A later algorithm must not silently rewrite a historical record.

`measurement.template.json` is a repository-ready draft record showing every major v1 field. `measurement.schema.json` is the JSON Schema Draft 2020-12 validator.