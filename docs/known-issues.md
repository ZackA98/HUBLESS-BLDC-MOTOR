# Known Issues — SATOR V1 Onshape Document

> Recorded from a view-only inventory on 2026-10-20. Fixes happen in Onshape (Zack's account); this list is the checklist.

| # | Issue | Where | Impact |
|---|---|---|---|
| 1 | Mate **Revolute 1** shows a red error (missing/failed reference) | Scooter Assembly | Assembly may not solve/update correctly; fix or suppress deliberately |
| 2 | Most top-level instances are named **Part 1 / Part 2** | Scooter Assembly | BOM and documentation cannot identify parts |
| 3 | BOM **Part number** and **Description** columns are completely blank (14 rows) | Scooter Assembly BOM | Repo BOM had to be rebuilt from tab names — see `bom/bom-draft.csv` |
| 4 | Duplicate tabs: Rear Left Motor Mount **Copy 1 / Copy 2**, Motor Assembly **Copy 1**, Part Studio 1 copies | Body&Motor Mounts / Motor Parts / Misc | Unclear which version is authoritative; archive or delete copies |
| 5 | Superseded iterations still sit beside current parts (Foot Rest V1/V2, Front Motor Mount V1) | Body&Motor Mounts | Risk of exporting/using the wrong version |
| 6 | No materials, mass properties, or dimensions recorded in part properties | All Part Studios | Structural analysis (DWG-M-001) must use labeled assumptions until set |
| 8 | **Rotor** part studio (Motor Parts) shows a red feature error on **Extrude 4** (red badge on "Features (11)") | Motor Parts / Rotor | Part may be broken; it is not instantiated in the Motor Assembly as designed |
| 9 | All five **Motor Assembly** instances are literally named **Part 1** (occurrence numbers `<1>`–`<5>`); the only ID path is the flattened BOM | Motor Parts / Motor Assembly | Verified 2026-10-20: Part 1 `<5>`=Tire, `<1>`=RotorMagnetInsert, `<3>`+`<2>`=Rotor plate ×2, `<4>`=Stator; Rotor is not instantiated |
| 10 | No separate magnet, winding, or bearing parts exist in the Motor Assembly (verified 2026-10-20); magnets are ~46 blocks modeled into the RotorMagnetInsert ring (~51 stator slots), windings represented by the slotted core | Motor Parts / Motor Assembly | BOM misc-tab items for separate Magnet / Copper Coil parts do not apply to the motor; bearings still unaccounted for elsewhere |
| 7 | Electrical system is not modelled or specified (no battery, ESC, wiring in CAD) | — | Wiring diagram DWG-E-001 is PROPOSED, not as-built |

## Suggested cleanup order in Onshape

1. Fix Revolute 1
2. Rename instances/parts descriptively
3. Fill in BOM part numbers/descriptions (or accept the repo BOM as the record)
4. Archive superseded/copy tabs into an "Archive" folder
5. Assign materials so mass properties become real
6. Export STEP (Scooter Assembly + Motor Assembly) and renders for this repo
