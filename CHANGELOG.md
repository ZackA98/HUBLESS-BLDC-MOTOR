# Changelog

All notable changes to this repository (the showcase/documentation project — CAD changes are made in the Onshape "SATOR V1" document and re-exported here).

## [Unreleased]

### Added
- LICENSE (MIT), CONTRIBUTING.md, issue/PR templates
- `docs/specifications.md` — verified vs assumed specification table
- `docs/assembly-guide.md` — assembly sequence (draft, from CAD structure)
- `docs/testing-plan.md` — planned bench/structural/road test programme (not yet performed)
- `docs/calculations.md` — wheel geometry and speed/load calculations with labelled assumptions
- `docs/safety.md` — battery, electrical, and fabrication safety notes
- `docs/roadmap.md` — project status, pending decisions, next milestones
- `cad/README.md` and `images/README.md` — what belongs there and the export checklist
- `drawings/system-block-diagram.svg` — DWG-E-002, proposed power/signal architecture
- `docs/electrical-pinout.md` — proposed pinouts + wire schedule (companion to DWG-E-001)
- `docs/cost-estimate.md` — build budget (labelled estimates)
- `docs/decisions/` — ADR-001 authoritative assembly, ADR-002 bearings, ADR-003 electrical parts, ADR-004 pole/slot counts (35 coils / 49 magnets — odd magnet count flagged as an open question)
- `bom/sourced-parts.csv` — purchased/COTS parts BOM
- `tests/test-log-template.md` — test log template with plan IDs
- `CITATION.cff` — citation metadata

## [0.1.0] — 2026-10-20 / 2026-10-21 (PR #1, branch showcase/sator-v1-draft)

### Added
- Showcase README with assembly structure, drawings table, known issues
- `drawings/wiring-diagram.svg` — DWG-E-001, proposed dual-motor wiring (not as-built)
- `drawings/static-load-forces.svg` — DWG-M-001, draft static load analysis (883 N single-wheel worst case)
- `bom/bom-draft.csv` — BOM rebuilt from the Onshape inventory (native BOM fields were blank)
- `docs/design-notes.md`, `docs/known-issues.md`, `.gitignore`

### Verified
- Motor Assembly internals inventoried and double-verified in Onshape (2026-10-20): per motor Stator ×1, Rotor ×1, Rotor plate ×2, Tire ×1; 5 instances, no mates; volumes/diameters recorded in the BOM
- Motor Assembly Copy 1 inventoried (2026-10-21): 35 copper coils + 49 magnets (from the Misc magnet studio) — contents differ from the main assembly; which is authoritative is an open decision
- Confirmed defects: Revolute 1 mate error (Scooter Assembly), Rotor studio Extrude 4 feature error, no materials assigned to any part
