# P9 Print-in-place hinge
Family: printed · Comes apart: no, it swings · Extra parts: none · Motion: swings · Best plastic: PLA or PETG

## What it is
- Both leaves and the pin print together, already joined.
- Knuckles of leaf A and leaf B alternate along the axis.
- 45° cone pins sit in cone sockets to hold them together.
- A gap all round stops them fusing.
- Where leaf B passes leaf A's barrel, it is cut back in an arc with the same gap, so it can swing.

## Use when
- Box lids, flip covers, small doors
- One print with no assembly

## Skip when (use instead)
- Heavy loads. The printed pin is small. Use H4, or a steel pin through printed knuckles.
- The hinge must be tight and precise. The gaps leave play.

## Sizes
| What | Guides | Ender 1.0 (guess) |
|---|---|---|
| Gap side to side (XY) | ≥ 0.3 · PLA/PETG 0.3–0.4 · ABS/ASA/nylon 0.4–0.5 | 0.5, test 0.4–0.6 |
| Gap above and below (Z) | ≥ 2 layers · 0.5–0.6 under a roof | 0.8 (2 layers) |
| Gaps in the first 2 layers | + 0.2, or start moving parts above layer 2 | start above layer 2 |
| Cone pin and socket | 45° | same |
| TPU | gap ≥ 0.5 (sticks to itself) | same |
| Barrel wall around the pin | — | ≥ 2.2 (2 lines) |

Practitioners report about 0.3 for PLA on an Ender 3 with a 0.4 nozzle. The 1.0 nozzle squashes wider lines, so start at 0.5 and print a small test hinge.

## Model it in SolidCraft
1. **Leaves:** lay out both leaves flat, with the hinge axis parallel to the bed (along X or Y).
2. **Knuckles:**
   - Barrel cylinders on the axis, alternating A, B, A…
   - Each barrel wall ≥ 2.2.
   - 0.5 axial gap between knuckles.
3. **Cone pins:**
   - On each A knuckle end, a 45° cone (`solid.cone` or a revolve) pointing into the neighbouring B knuckle.
   - Cut a matching cone socket, grown by 0.5.
4. **Cut-back:** cut each leaf back in an arc around the other leaf's barrel (barrel radius + 0.5), so it can rotate. Use `solid.revolve` with `operation: cut`, or an extruded arc.
5. **Z gaps:** keep the gaps above and below ≥ 0.8. No moving gap in the first 2 layers (0.84 from the bed).
6. Make A and B separate bodies. `inspect.clearance` with `clearance: 0.5` should list no pairs closer than 0.5.
7. `joint.create` type `revolute` on the barrel axis with `limits`, then sweep it to check the swing.

## Print it
- Lay the hinge axis flat on the bed.
- Break it free by turning it a few times while it is still warm.

## Check before done
- [ ] Gaps of 0.5 in XY and 0.8 in Z everywhere.
- [ ] Nothing moving in the first 2 layers.
- [ ] Cone angles 45°.
- [ ] Barrel walls ≥ 2.2.
- [ ] The swing sweep is clear.

## Fails → fix
| Problem | Fix |
|---|---|
| Fused, won't turn | Gap too small or squashed on the first layer: bigger gap, lift moving parts off the first layers |
| Stiff at first | Normal: turn it firmly a few times right after printing |
| Floppy | Gap too big: shrink in 0.05 steps |
| Strings across the gap (PETG) | Add 0.1 to the gap |

## Pairs well with
- P1 or P12 to hold the lid shut.
