# ADR-003 — Electrical parts selection

**Status:** Open — every electrical value in the repo is currently ASSUMED
**Date raised:** 2026-10-21

## Context

DWG-E-001 was drawn with placeholder values so the architecture could be documented: 48 V (13S) pack, 40 A fuse, two sensored ESCs, hall throttle, shared throttle signal, e-brake cut-off to both controllers. Nothing electrical is modelled or specified in the CAD.

## Decision needed

Choose, in order (each constrains the next):

1. **Battery:** voltage, capacity, cell format, BMS rating
2. **ESCs:** model, voltage/current rating, sensored support, whether dual ESCs accept a shared throttle signal or need master/slave config
3. **Throttle + e-brake:** parts matched to the ESCs
4. **Display** (optional)

## Consequences when decided

- DWG-E-001 Rev B replaces ASSUMED with as-selected values
- `docs/electrical-pinout.md` "typical" values get verified against datasheets
- `docs/calculations.md` gains Kv-based top-speed and range estimates
- `bom/sourced-parts.csv` electrical rows become purchasable
- Budget in `docs/cost-estimate.md` tightens from ranges to prices
