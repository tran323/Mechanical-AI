# H4 Bearing + shaft
Family: hardware · Comes apart: yes, and it turns · Extra parts: ball bearing, steel rod · Motion: turns under load · Best plastic: PETG or nylon pocket

## What it is
- A steel ball bearing sits in a printed pocket, and a steel rod goes through its middle.
- A shoulder below and a lip or screwed cap above hold the bearing in.
- Crush ribs take up print error.
- It turns smoothly for years.

## Use when
- Wheels, pulleys and rollers
- Knobs and arms that turn a lot or under load
- Anything that must turn smoothly for years

## Skip when (use instead)
- It turns slowly, lightly and rarely. A printed bushing on a steel pin is enough: 0.3–0.4 total gap, grease.
- There is no room for a bearing. Use P9 for light swings.

## Common bearings (d × D × B)
| Bearing | Bore d | Outside D | Width B | Typical use |
|---|---|---|---|---|
| 623 | 3 | 10 | 4 | small idlers, M3 shafts |
| 625 | 5 | 16 | 5 | 5 mm shafts |
| 688 | 8 | 16 | 5 | thin 8 mm parts |
| 608 | 8 | 22 | 7 | the common skateboard bearing |
| 6000 | 10 | 26 | 8 | 10 mm shafts |
| LM8UU | 8 | 15 | 24 | slides along an 8 mm rod |

## Sizes
| What | Guides | Ender 1.0 (guess) |
|---|---|---|
| Pocket Ø | D + 0 to 0.15 (after a test print) | test D + 0.1 to 0.2 |
| Crush ribs | 3–6 ribs · 0.1–0.2 squash per side | same |
| Holding it in | shoulder below + lip or screwed cap | same |
| Shaft | steel rod, never printed | same |
| Printed bushing instead | 0.2–0.4 total gap, grease, steel pin, slow | 0.3–0.4 |
| Pocket wall | — | ≥ 3.3 |

- Press only on the ring being fitted, never through the balls.
- With two bearings on one shaft, fix one and let the other float along the shaft. Space them apart to stop wobble.

## Model it in SolidCraft
1. **Pocket:** `solid.hole` with `diameter` = D + 0.15 (608: 22.15) and `depth` = B rounded up to the 0.4 grid (608: 7.2).
   - Wall around it ≥ 3.3.
2. **Shoulder:** a smaller through hole below, Ø ≈ D − 2 to 3, so the outer ring sits on a ledge without touching the seals.
3. **Crush ribs (optional):**
   - Make the pocket D + 0.4.
   - Add 3–6 thin half-round ribs inside that reach 0.1–0.2 past D: sketch, extrude, then `solid.pattern.circular` about the pocket axis.
4. **Retention:** a lip on top (a 45° chamfered overhang), or a cap held with H1, H2 or H3 screws.
5. **Shaft:** model the steel rod as a separate body (diameter = bore) for the hardware list. Never make it a printed part.
6. `joint.create` type `revolute` between shaft and pocket, then sweep it to check that nothing collides.

## Print it
- Print with the pocket axis straight up (Z). That is the roundest hole a printer makes.

## Check before done
- [ ] Bearing named.
- [ ] Pocket D + 0.1–0.2, depth on the grid.
- [ ] Shoulder, plus a lip or cap.
- [ ] Wall ≥ 3.3.
- [ ] The shaft is steel.
- [ ] Two bearings are spaced apart.

## Fails → fix
| Problem | Fix |
|---|---|
| Bearing loose in the pocket | Add crush ribs or reprint 0.05 smaller; PLA creeps: use PETG |
| Rough or warm | Pocket too tight is squeezing it: open it up |
| Pocket cracked | Too tight: use crush ribs instead |
| Shaft wobbles | Bearings too close: move them further apart |

## Pairs well with
- H3 for the cap.
- H2 to screw the cap on many times.
