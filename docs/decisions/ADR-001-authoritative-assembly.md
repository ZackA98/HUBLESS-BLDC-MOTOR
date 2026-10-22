# ADR-001 — Authoritative motor assembly

**Status:** Open — decision: Zack
**Date raised:** 2026-10-21

## Context

The Onshape document contains two motor assemblies:

- **Motor Assembly** (the one instanced ×2 in the Scooter Assembly): 5 parts — Stator, Rotor, 2× Rotor plate, Tire. **No magnets, no windings, no bearings instanced.** Verified twice, 2026-10-20.
- **Motor Assembly Copy 1:** the same base parts **plus** 35 copper coils and 49 magnets in circular patterns (verified 2026-10-21), one rotor plate suppressed.

Copy 1 looks like the more developed iteration, but the scooter uses the main assembly. Until one is chosen, BOM quantities for magnets/coils stay "Copy 1 only" and the assembly guide carries a warning.

## Decision needed

Pick one as authoritative. Suggested path: merge Copy 1's coil/magnet patterns into the main Motor Assembly, instance it in the scooter, and archive Copy 1.

## Consequences when decided

- `bom/bom-draft.csv` and `bom/sourced-parts.csv` quantities become final
- Assembly guide §A loses its warning banner
- STEP exports should be taken **after** the merge so the repo models match the decision
