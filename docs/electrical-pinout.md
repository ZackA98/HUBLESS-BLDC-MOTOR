# Electrical Pinout & Wire Schedule (PROPOSED)

> Companion to **DWG-E-001** (wiring diagram). The electrical system is **not modelled in CAD** — every pinout below is the *proposed/standard* arrangement, marked ASSUMED. **Verify against the actual ESC and motor datasheets before connecting power.** A mis-pinned Hall harness can damage a controller (see `docs/safety.md`).

## Power path

| From | To | Conductors | Wire (ASSUMED) | Notes |
|---|---|---|---|---|
| Battery pack + | BMS discharge + | — (internal) | — | Pack in chassis deck box |
| BMS + | Main fuse (40 A ASSUMED) | 1 | 10–12 AWG silicone | Fuse as close to pack as practical |
| Fuse | Power switch / anti-spark loop key | 1 | 10–12 AWG silicone | Doubles as service disconnect |
| Switch | DC bus split → ESC-Front, ESC-Rear B+ | 2 runs | 12 AWG silicone | Keep runs short, twisted with B− |
| Battery − (via BMS) | ESC B− ×2 | 2 runs | 12 AWG silicone | Common ground point at pack |

## Per motor (×2 — front and rear identical)

### Phase wires (ESC → motor)

| Pin | Signal | Colour (typical) |
|---|---|---|
| 1 | Phase U | Yellow |
| 2 | Phase V | Green |
| 3 | Phase W | Blue |

If a motor runs backwards or rough, swap any two phase wires and re-check the Hall sequence — do this at zero/low throttle on the bench only.

### Hall sensor bundle (motor → ESC)

| Pin | Signal | Colour (typical) |
|---|---|---|
| 1 | +5 V | Red |
| 2 | GND | Black |
| 3 | Hall A (H1) | Yellow |
| 4 | Hall B (H2) | Green |
| 5 | Hall C (H3) | Blue |

ASSUMED standard ordering — sensorless fallback exists on many ESCs if Halls are omitted, but sensored start-up is the design intent for a scooter (low-speed torque).

## Controls

| Device | Wires | Signal | Destination |
|---|---|---|---|
| Throttle (hall type, ASSUMED) | +5 V / GND / SIGNAL | 0.8–4.2 V typical | Signal split to **both** ESCs (dual-drive assumption in DWG-E-001) |
| E-brake lever switch | 2 | Cut-off (open/closed per ESC setting) | **Both** ESCs — unconfirmed in CAD, required before powered tests |
| Display (optional) | UART TX/RX + power | Per ESC vendor | One ESC only (master) if fitted |

## Open items

- [ ] ESC model selection fixes every "typical" value above (ADR-003)
- [ ] Confirm throttle signal split behaviour — some ESC pairs need a single master/slave arrangement instead
- [ ] Confirm e-brake polarity per ESC manual
