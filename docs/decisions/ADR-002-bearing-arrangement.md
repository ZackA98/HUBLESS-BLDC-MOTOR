# ADR-002 — Bearing / guide-roller arrangement

**Status:** Open — not modelled in CAD
**Date raised:** 2026-10-21

## Context

A hubless wheel must be located radially/axially by something: typically guide rollers or bearings running on the rotor ring, reacting the loads in DWG-M-001's load path (stator → rollers → rotor). In the SATOR V1 CAD:

- A "5mm Ball Bearing" part studio exists in Misc
- **No bearing or roller is instanced in either motor assembly**
- The main Motor Assembly has **zero mates**, so nothing currently constrains the rotor relative to the stator

## Decision needed

Define the arrangement: how many rollers/bearings per wheel, their positions, what surface they run on, and how the air gap is set and held. Then model it (with mates) so the static-load drawing's R1/R2/R3 reaction split can be computed instead of left qualitative.

## Consequences when decided

- DWG-M-001 Rev B can distribute the 883 N case across real reaction points
- Sourced-parts BOM item 3 gets a real quantity/spec
- Structural test S1 gains a measurable deflection target
