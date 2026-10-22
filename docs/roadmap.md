# Roadmap & Project Status

_Last updated 2026-10-21._

## Where V1 stands

- ✅ Full CAD model in Onshape: scooter with dual hubless wheel motors
- ✅ Engineering showcase repo: README, verified BOM, design notes, known issues, drawings (wiring + static loads)
- ✅ Motor Assembly **and** Motor Assembly Copy 1 fully inventoried
- ⏳ CAD exports/renders for the repo — needs an export from the Onshape account (document is view-only when link-shared)
- ⏳ Physical build — not started / not documented yet

## Decisions needed (Zack)

1. **Authoritative motor design:** main Motor Assembly (no magnets/windings instanced) vs **Copy 1** (35 coils + 49 magnets patterned). Copy 1 looks like the developed iteration — confirm, then merge its content into the main assembly and retire the copy.
2. **Electrical parts:** battery pack (voltage/capacity), ESC model, throttle — everything electrical is currently ASSUMED in DWG-E-001.
3. **Bearing/guide-roller arrangement:** not modelled in the main assembly yet — design or document the intended hardware.
4. **PR #1:** review and merge the showcase draft to `main` when satisfied.

## CAD cleanup (in Onshape)

- [ ] Fix Revolute 1 mate error (Scooter Assembly)
- [ ] Fix Rotor studio Extrude 4 feature error
- [ ] Rename Part 1/Part 2 instances descriptively
- [ ] Assign materials → real mass properties
- [ ] Add mates to Motor Assembly (currently 0 — parts float)
- [ ] Archive superseded tabs (Foot Rest V1/V2, Motor Mount V1, stray copies)
- [ ] Fill Onshape BOM part numbers/descriptions (or keep repo BOM as the record)

## Milestones after decisions

1. STEP exports + renders into `cad/` and `images/`; README hero image
2. Rev B of DWG-M-001 with dynamic factor; Rev B of DWG-E-001 with real parts
3. Bench-test programme (`docs/testing-plan.md` §1) once hardware exists
4. Structural tests (§2), then — and only then — vehicle tests (§3)

## Ideas parked for V2

- Regenerative braking via ESC configuration
- Integrated lighting on the deck/stem
- Swappable battery pack in the deck box
- Torque/speed logging for real W/mi data
