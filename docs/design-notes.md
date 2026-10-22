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

## Motor Assembly internals (verified 2026-10-20)

Each Motor Assembly contains exactly **5 part instances and no mates at all** — parts are positioned but unconstrained:

| Part | Qty per motor | Measured |
|---|---|---|
| Stator | 1 | Volume 100.692 in³ |
| Rotor | 1 | OD 8.200 in, volume 71.569 in³ |
| Rotor plate | 2 (front + back disc) | Center hole Ø 5.200 in, volume 10.985 in³ each |
| Tire | 1 | OD 12.700 in, volume 410.767 in³ |

Key findings:

- **No material is assigned to any part**, so Onshape cannot compute mass — the mass-properties dialog warns and leaves Mass blank.
- The **RotorMagnetInsert studio exists but is NOT instanced** in Motor Assembly, and **no bearings appear in the assembly at all** — as modelled, the main Motor Assembly has neither magnets nor a bearing/roller arrangement.
- **Motor Assembly Copy 1 differs significantly**: 9 instances and two circular patterns, verified 2026-10-21 via each instance's "Switch to \<studio\>" context menu (which names its source Part Studio). **"Circular pattern 1" is 35 copper coils** (seed instance Part 1 \<6\>), sourced from the "Copper Coil" studio — the earlier note describing these blocks as magnets was a misidentification. **"Circular pattern 2" is 49 magnets**, thin bars sourced from the "6 in x 1/8 in x 5/16 Magnet" studio (RotorMagnetInsert was ruled out as the pattern source). Also present: a standalone magnet-like bar (Part 1 \<42\>, source unconfirmed in view-only mode) and a Rotor plate instance (Part 1 \<2\>) that is suppressed in Copy 1 but active in the main assembly. Copy 1 looks like a later/alternate iteration that was never merged back into the main assembly. Which one is authoritative is a design decision for Zack.

## Electrical (PROPOSED — see drawings/DWG-E-001)

- Dual sensored BLDC drive, one ESC per motor, common battery bus and throttle signal — ASSUMED architecture
- Battery voltage/capacity, ESC model, motor Kv/winding: **TBD — not recorded in the CAD document**

## Structural (DRAFT — see drawings/DWG-M-001)

- Load path: rider → deck/chassis → motor mounts → stator → guide rollers/bearings → rotor + tire ring → ground
- Draft static case: 883 N (≈90 kg) on a single wheel, worst case, no dynamic factor

## Open design questions

1. Are both motors driven, or is one a design placeholder carried over by copying the assembly?
2. What ESC and battery are intended? Nothing electrical is modelled except the copper coil.
3. What is the intended roller/bearing arrangement? Verified 2026-10-20: the main Motor Assembly contains **no bearings and no magnets at all** — only Stator, Rotor, 2× Rotor plate, Tire, with zero mates. Verified 2026-10-21: Motor Assembly Copy 1 contains 49 magnet instances (from the "6 in x 1/8 in x 5/16 Magnet" studio) and 35 copper coil instances, plus one suppressed Rotor plate. Decide which assembly is the real design, then merge the magnet/bearing content into it.
4. Steering: how does the front Motor Assembly mount handle steering pivot loads (front mounts + steering mount tab exists)?
