# SATOR V1 — Specifications

> Rule for this table: **VERIFIED** = measured in the Onshape document (2026-10-20/21) or otherwise evidenced. **ASSUMED / TBD** = design intent or placeholder — never quote these as measured.

## Geometry (VERIFIED from Onshape)

| Item | Value | Source |
|---|---|---|
| Tire outer diameter | 12.700 in (322.6 mm) | Tire studio / Motor Assembly mass properties |
| Tire volume | 410.767 in³ | Motor Assembly |
| Rotor outer diameter | 8.200 in (208.3 mm) | Rotor studio |
| Rotor volume | 71.569 in³ | Motor Assembly |
| Stator volume | 100.692 in³ | Motor Assembly |
| Rotor plate (each) | Center hole Ø 5.200 in; volume 10.985 in³ | Rotor plate studio |
| Wheels / motors | 2 (front + rear), both Motor Assembly instances | Scooter Assembly |
| Parts per Motor Assembly | 5: Stator ×1, Rotor ×1, Rotor plate ×2, Tire ×1 | Instance tree, "Switch to" menus |
| Mates in Motor Assembly | 0 (parts positioned, unconstrained) | Assembly tree |
| Materials assigned in CAD | None — mass cannot be computed | Mass properties warning |

## Alternate iteration — Motor Assembly Copy 1 (VERIFIED contents, status TBD)

| Item | Qty | Source studio |
|---|---|---|
| Copper coils (circular pattern 1) | 35 | Misc / Copper Coil |
| Magnets (circular pattern 2) | 49 | Misc / 6 in × 1/8 in × 5/16 in Magnet |
| Standalone magnet-like bar | 1 | Unconfirmed |
| Rotor plate | 1 suppressed of 2 | Rotor plate studio |

Which assembly is authoritative — main Motor Assembly or Copy 1 — is an **open decision** (see roadmap).

## Electrical (ALL ASSUMED / TBD — see DWG-E-001)

| Item | Value | Status |
|---|---|---|
| Battery | 48 V nominal (13S Li-ion) | ASSUMED |
| Main fuse | 40 A | ASSUMED |
| ESCs | 2× sensored BLDC controllers, model TBD | TBD |
| Motors driven | Both wheels | ASSUMED |
| Throttle | Hall-effect type | ASSUMED |
| E-brake cut-off | Intended | Unconfirmed in CAD |

## Loads (DRAFT analysis — see DWG-M-001)

| Item | Value | Status |
|---|---|---|
| Design static load case | 883 N (≈90 kg) on a single wheel, worst case | ASSUMED mass, DRAFT calc |
| Dynamic/impact factor | Not included yet | TBD |
