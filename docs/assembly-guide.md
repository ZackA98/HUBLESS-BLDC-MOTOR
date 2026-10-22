# Assembly Guide (DRAFT)

> Derived from the CAD structure in Onshape on 2026-10-21. This describes the assembly order the CAD implies — it has **not** been validated against a physical build. Quantities are per the verified BOM (`bom/bom-draft.csv`).

## Subassembly A — Motor Assembly (build ×2: front + rear)

Current CAD content per motor: Stator ×1, Rotor ×1, Rotor plate ×2, Tire ×1.

1. Press/fit the **Tire** onto the **Rotor** ring (rotor OD 8.200 in, tire OD 12.700 in).
2. Seat the **Stator** concentrically inside the rotor bore — air gap is the critical dimension; the CAD currently has **no mates** in this assembly, so concentricity must be set deliberately when mates are added.
3. Fit **Rotor plates** (front + back) to close the wheel; plates have a Ø 5.200 in centre hole for the axle/mount interface.
4. ⚠️ **Open items in this subassembly:** the magnet insert and copper windings exist as studios (and fully patterned in Motor Assembly Copy 1: 49 magnets, 35 coils) but are **not yet merged** into the main Motor Assembly. Bearing/guide-roller arrangement is likewise not yet modelled. Do not treat this sequence as final until those are resolved.

## Subassembly B — Chassis

1. **Base Plate** to **Chassis** (battery deck).
2. **Foot Rest (V3)** to the deck. (V1/V2 are superseded — do not use.)
3. **Stem** (steering) to the front of the chassis; front fork with coil-over shock per the Scooter Assembly.

## Final assembly

1. Mount front **Motor Assembly** via the front motor mounts (Left + Right, V2) to the fork/steering.
2. Mount rear **Motor Assembly** via the rear motor mounts (Left + Right) to the chassis.
3. ⚠️ Top-assembly mate **Revolute 1** currently errors in Onshape — resolve before using the CAD to check clearances/interference.
4. Electrical fit-out follows **DWG-E-001** (proposed): battery in the deck box → fuse → switch → dual ESCs → phase + Hall wiring to each motor; throttle signal split to both ESCs. **Verify Hall pinouts on the actual controllers before power-up** (see drawing notes and `docs/safety.md`).
