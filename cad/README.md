# CAD Exports

STEP exports from the Onshape document **"SATOR V1"** belong here. The Onshape document is the source of truth; files in this folder are snapshots of it.

## Expected files

| File | Source tab in Onshape | Status |
|---|---|---|
| `scooter-assembly.step` | Scooter Assembly (top assembly) | ⏳ Awaiting export |
| `motor-assembly.step` | Motor Assembly | ⏳ Awaiting export |
| `motor-assembly-copy-1.step` | Motor Assembly Copy 1 (alternate iteration) | ⏳ Awaiting export — optional |

## Export checklist (in Onshape)

1. Fix or consciously accept the known errors first (Revolute 1 mate; Rotor Extrude 4) — see `docs/known-issues.md`
2. Right-click the assembly tab → **Export…** → format **STEP (AP214)**, units mm or in (note which in the commit message)
3. Name the file as above and drop it in this folder
4. Also export one shaded render per assembly into `images/` (PNG, largest available size)

## Viewing

GitHub renders STL natively; STEP files can be converted to GLB for in-browser viewing. Large binaries may move to GitHub Releases instead of git history.
