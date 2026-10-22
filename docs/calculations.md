# Calculations

> Engineering estimates for the SATOR V1. Inputs are VERIFIED geometry from Onshape unless marked ASSUMED. These are design-stage estimates, not test results.

## 1. Wheel geometry (VERIFIED inputs)

- Tire outer diameter D = 12.700 in = 0.32258 m
- Rolling circumference C = π × D = **1.0134 m** (39.90 in)
- Rotor outer diameter = 8.200 in (208.3 mm) → rim-drive ratio is inherent to the layout; torque is applied at the rotor radius ≈ 0.104 m

## 2. Road speed vs wheel speed

v (km/h) = RPM × C × 60 / 1000 = RPM × 0.0608

| Wheel RPM | Speed (km/h) | Speed (mph) |
|---|---|---|
| 200 | 12.2 | 7.6 |
| 400 | 24.3 | 15.1 |
| 600 | 36.5 | 22.7 |
| 800 | 48.6 | 30.2 |
| 1000 | 60.8 | 37.8 |

Once a motor Kv and battery voltage are chosen (currently TBD), no-load RPM ≈ Kv × V and the table gives the corresponding top-speed estimate (before losses/load).

## 3. Static load case (summary of DWG-M-001)

- ASSUMED total load (rider + vehicle): 90 kg → W = 90 × 9.81 = **883 N**
- Worst case: 100% of W on one wheel → ground reaction R = 883 N (ΣFy = 0)
- Load path: rider → deck/chassis → motor mounts → stator → guide rollers/bearings → rotor + tire ring → contact patch → ground
- The split between guide rollers R1/R2/R3 needs measured roller geometry + stiffness — still open.
- **Not yet included:** dynamic/impact factor (curb strikes, potholes). A factor of 2–3× on the static case is a common starting assumption for small-wheel vehicles — to be applied explicitly in Rev B of DWG-M-001.

## 4. Motor content (from the Copy 1 inventory, VERIFIED counts)

- Copper coils: 35 per motor (Copy 1 pattern 1)
- Magnets: 49 per motor (Copy 1 pattern 2, 6 in × 1/8 in × 5/16 in stock)
- These counts belong to the alternate assembly; if Copy 1 becomes authoritative, winding/pole analysis goes here.

## 5. Open calculations

- [ ] Torque at the wheel vs gradeability (needs motor Kt/Kv + ESC current limit)
- [ ] Battery range estimate (needs pack capacity + measured W/mi from testing)
- [ ] Guide-roller Hertzian contact stress (needs roller geometry/materials)
- [ ] Rotor plate bolted-joint check (needs fastener spec + materials)
