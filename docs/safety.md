# Safety Notes

> The SATOR V1 combines a lithium battery pack, high-current motor controllers, and a rider-carrying structure. These notes are part of the design record — read them before building, wiring, or testing.

## Battery & electrical

- Treat the (ASSUMED 48 V / 13S) pack as always live. 48 V DC can sustain arcs and serious burns on a short circuit.
- The main fuse in **DWG-E-001** is not optional — fit it before any powered test, sized to the final wiring/ESC choice (40 A is an assumed placeholder, not a specification).
- Use the anti-spark/loop-key disconnect shown in DWG-E-001; disconnect before any wiring change.
- **Verify Hall sensor and phase wiring pinouts on the actual ESCs before first power-up.** A mis-pinned Hall harness can drive a motor violently or destroy a controller.
- Charge Li-ion only with a correct-voltage balance charger, on a non-flammable surface, never unattended. Inspect for swelling/damage before every use; a damaged pack is retired, not repaired.
- No water exposure until the deck/ESC enclosures are sealed and tested.

## Mechanical / structural

- **DWG-M-001 is a draft static analysis with an assumed load** — it is not a certification. The real structure (mounts, plates, guide rollers) must pass the physical load tests in `docs/testing-plan.md` before anyone rides it.
- The Rotor studio has an unresolved feature error (Extrude 4) and the main Motor Assembly currently models no bearings/guide rollers — resolve the design before cutting metal.
- Check fastener torque after the first runs and periodically thereafter; hubless wheels concentrate load in the mount/roller path.

## Riding / testing

- Helmet and closed shoes for any powered test; first powered runs in an open area away from traffic and people.
- Verify the e-brake cut-off works before the first powered run, and re-test after any wiring change.
- One change at a time during testing; log what changed (see testing plan).

## Fabrication

- Standard shop PPE for welding/machining; guard rotating parts during bench spins — a hubless rotor at speed is an exposed ring.
- Keep magnets away from pacemakers, cards, and loose steel tools; large magnets pinch hard.
