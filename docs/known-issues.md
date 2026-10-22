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
| 8 | **Rotor** part studio (Motor Parts) shows a red feature error on **Extrude 4** (red badge on "Features (11)") | Motor Parts / Rotor | Part still computes (volume measurable) and IS instanced in the Motor Assembly, but the failed feature should be fixed before relying on the geometry |
| 9 | All five **Motor Assembly** instances are literally named **Part 1** (occurrence numbers `<1>`–`<5>`) | Motor Parts / Motor Assembly | Mapping verified 2026-10-20 via "Switch to" source-studio menus + volume fingerprints: `<1>`=Stator, `<2>`=Rotor plate, `<3>`=Rotor plate, `<4>`=Tire, `<5>`=Rotor. Rename parts so this is self-evident |
| 10 | **RotorMagnetInsert is not instanced** in the Motor Assembly, and no bearings or separate winding parts exist in it either (verified 2026-10-20) | Motor Parts / Motor Assembly | As modelled, the main Motor Assembly has no magnets and no bearing arrangement. Verified 2026-10-21: Motor Assembly Copy 1 contains the full magnet/bearing content — 49 magnet instances from the "6 in x 1/8 in x 5/16 Magnet" studio ("Circular pattern 2") and 35 copper coil instances from the "Copper Coil" studio ("Circular pattern 1"). RotorMagnetInsert is NOT the pattern source. Decide which assembly is authoritative and merge the content |
| 7 | Electrical system is not modelled or specified (no battery, ESC, wiring in CAD) | — | Wiring diagram DWG-E-001 is PROPOSED, not as-built |

## Suggested cleanup order in Onshape

1. Fix Revolute 1
2. Rename instances/parts descriptively
3. Fill in BOM part numbers/descriptions (or accept the repo BOM as the record)
4. Archive superseded/copy tabs into an "Archive" folder
5. Assign materials so mass properties become real
6. Export STEP (Scooter Assembly + Motor Assembly) and renders for this repo
