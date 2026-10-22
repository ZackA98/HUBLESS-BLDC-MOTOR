# Contributing

This is Zackary Aebersold's personal engineering showcase for the SATOR V1 hubless BLDC scooter. Issues, questions, and suggestions are welcome — especially from anyone who has built hubless/rim-drive wheels before.

## Ways to help

- **Design review** — spot problems in the drawings, BOM, or calculations? Open an issue with the file/drawing number.
- **CAD feedback** — the source of truth is the Onshape document "SATOR V1". This repo holds exports and documentation, so CAD change suggestions are best filed as issues describing the change; the fix lands in Onshape and is re-exported.
- **Documentation** — corrections and clarifications via pull request are welcome.

## Ground rules

1. **Never present an assumption as a measurement.** This repo distinguishes VERIFIED values (measured in Onshape or on hardware) from ASSUMED/TBD values. Keep that labelling in anything you add.
2. **Cite the source** for numbers: Onshape tab/studio name, drawing number (e.g. DWG-M-001), or a test record.
3. **Small, focused PRs** — one change per PR, with a sentence on why.
4. Binary CAD exports (STEP/STL) are published under `cad/`; large binaries go in GitHub Releases, not git history.

## Repo layout

See the README's "Repo Contents" section; design decisions live in `docs/`.
