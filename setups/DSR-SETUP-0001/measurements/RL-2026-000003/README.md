# Vibration Measurement

## Identity

**Measurement ID:** RL-2026-000003  
**Measurement UUID:** `efb8a878-364d-4ac7-8ce4-66b886d004e3`  
**Setup:** DSR-SETUP-0001  
**Measured:** 22 August 2026 at 23:38  
**Timezone:** Europe/London

## Vibration Context

**Support:** Wall shelf  
**Support description:** Not recorded  
**Isolation:** None  
**Isolation description:** Not recorded  
**Floor:** Suspended timber floor  
**Floor description:** Not recorded  
**Phone position:** Platter  
**Phone orientation:** portrait  
**Phone placement note:** Not recorded  
**Motor:** Off  
**Platter:** Stationary  
**Record:** Not present  
**Stylus:** Not tracking  
**Speakers:** Active  
**Environment note:** Not recorded  
**Playback-level note:** Not recorded

## Results

**Capture RMS:** 1.362 mg  
**Capture Peak:** 9.536 mg  
**Analysis range:** 1–40 Hz

| Band | Energy | RMS |
| --- | ---: | ---: |
| 1–8 Hz | 11.73 % | 0.451 mg |
| 8–20 Hz | 21.64 % | 0.612 mg |
| 20–40 Hz | 66.62 % | 1.074 mg |

Legacy band RMS estimator; values preserved as originally analysed.

## Dominant Peaks

- 34.07 Hz · 0.216 mg
- 38.15 Hz · 0.212 mg
- 39.03 Hz · 0.201 mg
- 36.11 Hz · 0.199 mg
- 33.09 Hz · 0.188 mg

## Prediction and Vibration Context

**Calculated resonance:** 6.89 Hz  
**Comparison region:** 5.89–7.89 Hz  
**Resonance position:** Below preferred  
**Frequency coverage:** Full  
**Measurement state:** Valid Vibration measurement  
**Peak relationship:** Dominant peaks elsewhere  
**Confidence:** Limited  
**Coarse assessment:** Not assessed

The calculated cartridge/tonearm resonance is 6.89 Hz, below the preferred 8–12 Hz region.

The measured vibration spectrum contains dominant local peaks, at higher frequencies (34.07 Hz, 38.15 Hz, and 39.03 Hz), but measurement confidence was insufficient to classify a significant feature near the predicted resonance region. Most measured vibration energy lies above the predicted comparison region.

**Recommendations:**

- Repeat the measurement if stronger evidence near the predicted resonance region is required. Address the recorded confidence limitation: Overall vibration was within 3 dB of the measured pre-capture floor.
- If you want to raise the calculated resonance, reduce total moving mass where practical or consider a lower-compliance cartridge; evaluate that calculation separately from the phone vibration result.

> **Scientific limitation:** The phone measures mechanical vibration at its placement point. This contextual comparison does not directly measure or prove cartridge/tonearm or stylus/cantilever resonance, acoustic feedback, motor/bearing resonance, structural resonance, a specific cause, or causation. The ±1.0 Hz comparison window is a deterministic comparison rule, not a precision claim.

## Measurement Provenance

**Application:** Resonance Lab 1.0  
**Device:** iPhone16,1  
**Operating system:** iOS 26.6.1  
**Analysis method:** vibration-1-40-1.0.0

## Attribution

**Measurement author:** Anonymous contributor  
**Publisher:** Direct Sound Records

## Citation

Anonymous contributor. “Rega P3 / Rega RB330 / Audio-Technica AT-OC9XML — Measurement, 22 August 2026.” Resonance Lab Measurement RL-2026-000003. Published by Direct Sound Records.

## Data Files

- `vibration/spectrum.csv`

> **Archive note:** Derived report/images are retained in the source submission package; the canonical GitHub record publishes the structured JSON and CSV evidence used for machine-readable analysis.

> **Source-submission note:** The original Reference Package contains the full stored time series. The canonical GitHub record mirrors the structured JSON and spectrum CSV; source-package identity and SHA-256 are preserved in the public measurement index.
