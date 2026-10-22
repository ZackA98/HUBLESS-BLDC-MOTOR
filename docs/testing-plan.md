# Testing Plan (PLANNED — no tests performed yet)

> Every test here is a plan, not a result. When a test is run, record date, setup, measured values, and pass/fail in a `tests/` log and link it from here. Never back-fill planned values as results.

## 1. Motor bench tests (per motor, before vehicle integration)

| # | Test | Method | Pass criterion |
|---|---|---|---|
| B1 | Phase continuity/resistance | Multimeter across U/V/W pairs | Balanced readings, no opens/shorts |
| B2 | Hall sensor function | Rotate rotor slowly, scope/LED on Hall outputs | Clean switching on all 3 channels, correct sequence |
| B3 | No-load spin | Bench supply, ESC at low throttle | Smooth rotation, no rubbing (air-gap check), no abnormal noise |
| B4 | No-load current vs RPM | Tach + current meter across the throttle range | Curve recorded; no current spikes |
| B5 | Thermal soak | Sustained moderate load, IR thermometer on stator/ESC | Temperatures stabilise below component ratings (ratings TBD with ESC choice) |
| B6 | Dual-motor sync | Both ESCs on the shared throttle signal (per DWG-E-001) | Both wheels track without fighting/surging |

## 2. Structural tests

| # | Test | Method | Pass criterion |
|---|---|---|---|
| S1 | Static load | Apply the DWG-M-001 design case (883 N at the contact patch, single wheel) via weights/press | No visible deflection/permanent set; compare with guide-roller reactions |
| S2 | Impact/drop | Controlled drop from a set height (TBD) | No cracking, loosening, or air-gap contact |
| S3 | Fastener torque check | Torque wrench on mount/plate hardware after S1–S2 | No fastener movement |

## 3. Vehicle tests (only after 1–2 pass)

| # | Test | Notes |
|---|---|---|
| V1 | Low-speed roll test | Push test, wheels free-spin true, steering centred |
| V2 | Powered low-speed run | Empty area, helmet, e-brake cut-off verified first (see safety.md) |
| V3 | Range/thermal run | Log battery voltage sag, motor/ESC temps |
| V4 | Hill/grade behaviour | Relevant to Sacramento terrain; log current draw |

## Open prerequisites

- ESC and battery selection finalised (all electrical values currently ASSUMED)
- Materials assigned in CAD so mass properties are real
- Authoritative motor design chosen (main Motor Assembly vs Copy 1)
