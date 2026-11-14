# P7 Dovetail & T-slot (sliding tongue)
Family: printed · Comes apart: slides out the way it went in · Extra parts: none · Holding: medium; strong when glued · Best plastic: PETG or PLA

## What it is
- A shaped tongue slides into a matching slot. It lines parts up and can't pull straight apart.
- **Dovetail:** angled sides.
- **T-slot:** a T-shaped head.
- **Flexible T:** thin flanges that press for a no-wobble fit.

## Use when
- Joining sections of a print too big for the bed
- Sliding lids, drawers and rails
- Mounts that slide on: cameras, tools, holders

## Skip when (use instead)
- Only a plain square tongue fits. It is weak, so glue it (P8).
- It must carry a bending load. It needs extra length, 2 keys and a stop, or H3.

## Sizes
| What | Guides | Ender 1.0 (guess) |
|---|---|---|
| Sliding gap | 0.20–0.30 per side | 0.3 |
| Dovetail sides | 15° per side (10–20°) | same |
| Overhanging face if the slot prints open-side up | ≤ 45° | same |
| Taper along the slide | 1–2°: loose start, tight finish | same |
| Chamfer on tongue tip and slot mouth | 45° × 0.5–1.0 | 45° × 0.8–1.2 |
| Inside slot corners | round reliefs (FDM can't print sharp inside corners) | relief Ø ≥ 1.1 |
| Flexible T flanges | 0.9–1.35 thick · press 0.3–0.5 | 1.1–2.2 thick · same press |
| Carrying load | engaged length ≥ 1.5 × section height, 2 keys, a stop | same |

## Model it in SolidCraft
1. **Big print?** First `solid.split_body` with a plane where the joint goes.
2. **Tongue:**
   - Sketch the dovetail profile (15° sides) on the end plane of part A.
   - `solid.extrude` it along the slide length with `operation: join`.
3. **Slot:**
   - Sketch the same profile on part B and `sketch.offset` it outward by 0.3.
   - Add round reliefs (Ø ≥ 1.1) in the inside corners.
   - `solid.extrude` with `operation: cut`.
4. **Optional taper:** make the slot 1–2° narrower toward the far end, using a loft or a tilted cut, so the fit tightens as it slides home.
5. **Chamfers:** `solid.chamfer` the tongue tip and the slot mouth, 45° × 0.8–1.2.
6. **Flexible T:** make 1.1–2.2-thick flanges that overlap the slot wall by 0.3–0.5. That grip is intended.
7. **Load-bearing:** engaged length ≥ 1.5 × section height, 2 keys, and an end stop. Add glue (P8) for permanent joints.
8. **Optional check:** `joint.create` type `slider` and sweep it.

## Print it
- Run the slide along Z, or lay the profile in XY so no face overhangs more than 45°.
- Chamfer bed-side edges against elephant foot.

## Check before done
- [ ] Gap 0.3 per side.
- [ ] 15° sides.
- [ ] No overhang past 45° as printed.
- [ ] Inside corner reliefs.
- [ ] Lead-in chamfers.
- [ ] Load case has length, keys and a stop.

## Fails → fix
| Problem | Fix |
|---|---|
| Wobbles | Gap too big: add a 1–2° taper or use the flexible T-slot |
| Too tight to slide | Open to 0.3 per side, chamfer the slot mouth |
| Slot top spreads open | Make the slot deeper or add a cross-bar |
| T-bar first layer curls (ABS/ASA) | Use an eye-shaped slot: the round first layer resists warping |
| Flexible flanges go slack (PLA) | PLA creeps: use PETG |

## Pairs well with
- P8 glue for big prints.
- P6 pins to line the pieces up.
- P1 as an end stop.
