# ADR-004 — Pole/slot counts: 35 coils, 49 magnets (open design-review question)

**Status:** ⚠️ Open question — raised 2026-10-21 from the Copy 1 inventory. **This is a question, not a verified flaw.**

## Observation (VERIFIED counts)

Motor Assembly Copy 1 contains, per motor:

- **35 copper coils** (Circular pattern 1, from the Copper Coil studio)
- **49 magnets** (Circular pattern 2, from the 6 in × 1/8 in × 5/16 in Magnet studio)

## Why it's flagged

In a conventional 3-phase BLDC:

- Magnets alternate N/S around the rotor, so the **pole count is essentially always even** (poles come in N–S pairs). **49 is odd.**
- Coil/slot counts relate to pole counts by winding-layout rules (e.g. 12 slots/10 poles, 36/30, 42/36…). 35 coils is also an unusual count next to 49 magnets.

## Possible explanations (all unverified)

1. One pattern instance is a **spacer, marker, or index magnet** (e.g. for a speed sensor) rather than a working pole
2. A pattern count includes a **seed/overlap instance** that isn't a distinct physical part
3. The counts are **placeholders** — the patterns were made to look right before the winding design was finalised
4. A genuinely unconventional winding scheme (would need the layout documented)

## What would resolve it

- Zack confirms design intent, or
- Count distinct magnet instances and check polarity alternation in the model, and
- Document the intended slot/pole combination and winding layout in `docs/calculations.md`

Raised in the spirit of design review: if it's intentional, one sentence here closes it; if not, this is exactly the kind of thing to catch before winding 70 coils.
