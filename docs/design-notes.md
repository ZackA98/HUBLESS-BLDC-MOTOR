# SATOR V1 — Design Notes

> Compiled 2026-10-20 from the Onshape "SATOR V1" document inventory. Anything not directly observed in Onshape is marked ASSUMED / TBD.

## Concept

Stand-up electric scooter with **hubless BLDC motors in both wheels**. Removing the hub/axle from the wheel centre leaves a large open bore; torque is delivered at the rim by a stator/rotor pair integrated into the wheel, and the wheel is located by guide rollers/bearings running against the ring.

## Observed design (Onshape, verified)

- **Top assembly:** Scooter Assembly — chassis/deck (battery box) with raised tail, steering stem, coil-over shock front fork, 2× Motor Assembly (front + rear)
- **Motor group:** Stator, Rotor, RotorMagnetInsert, Rotor plate, Tire — all separate Part Studios under "Motor Parts"
- **Structure group:** Base Plate, Stem, Chassis, Foot Rest (V3 is latest of V1–V3), front motor mounts at V2, rear motor mounts with duplicate "Copy" tabs still in the document
- **Modelled purchased parts:** 5 mm ball bearings, 6" × 1/8" × 5/16" magnets, copper coil (stator winding representation)
- **Mates (top assembly):** 8 mates — 6 Fastened, 2 Revolute

## Electrical (PROPOSED — see drawings/DWG-E-001)

- Dual sensored BLDC drive, one ESC per motor, common battery bus and throttle signal — ASSUMED architecture
- Battery voltage/capacity, ESC model, motor Kv/winding: **TBD — not recorded in the CAD document**

## Structural (DRAFT — see drawings/DWG-M-001)

- Load path: rider → deck/chassis → motor mounts → stator → guide rollers/bearings → rotor + tire ring → ground
- Draft static case: 883 N (≈90 kg) on a single wheel, worst case, no dynamic factor

## Open design questions

1. Are both motors driven, or is one a design placeholder carried over by copying the assembly?
2. What ESC and battery are intended? Nothing electrical is modelled except the copper coil.
3. What is the intended roller/bearing arrangement inside the Motor Assembly — quantities are still TBD in the BOM.
4. Steering: how does the front Motor Assembly mount handle steering pivot loads (front mounts + steering mount tab exists)?
