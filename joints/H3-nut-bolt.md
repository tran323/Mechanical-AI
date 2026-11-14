# H3 Nut + bolt
Family: hardware · Comes apart: many times · Extra parts: bolt and nut · Holding: strongest · Best plastic: any (PETG for clamps)

## What it is
- A metal bolt goes through clearance holes in both parts into a metal nut.
- The nut sits in a hex nut trap so it can't spin.
- Metal threads do all the work, so this is the strongest joint here.
- The head sits in a counterbore. A metal sleeve stops plastic creep in clamped joints.

## Use when
- Brackets, frames and mounts
- Anything pulled, shaken or loaded
- Joints taken apart again and again

## Skip when (use instead)
- There is no room for the nut or the tool.
- The user wants a clean outside with no nut showing. Use H2.

## Sizes by bolt
| Size | M2 | M2.5 | M3 | M4 | M5 |
|---|---|---|---|---|---|
| Clearance hole | 2.4 | 2.9 | 3.4 | 4.5 | 5.5 |
| Socket head Ø × height | 3.8 × 2 | 4.5 × 2.5 | 5.5 × 3 | 7 × 4 | 8.5 × 5 |
| Nut across flats × height | 4.0 × 1.6 | 5.0 × 2.0 | 5.5 × 2.4 | 7.0 × 3.2 | 8.0 × 4.7 |
| Nut trap (flats + 0.25) | 4.25 | 5.25 | 5.75 | 7.25 | 8.25 |

| What | Guides | Ender 1.0 (guess) |
|---|---|---|
| Counterbore for the head | head Ø + 0.5–1.0 · depth head + 0.2–0.5 | same, depth on the 0.4 grid |
| Nut trap | flats + 0.2–0.3 · depth nut + 0.2–0.5 | flats + 0.3 |
| Side-entry nut slot | flats + 0.3 wide | same |
| Hole running sideways | + 0.1–0.2 | same |
| Bolt length | grip + nut + 1–2 threads | same |
| Which size | M3 for most · M2 small and light · M4 real load | same |

Against shaking, use a nylon-insert lock nut. Split washers do little. Some thread-locking glues crack PETG and ABS, so check first.

## Model it in SolidCraft
1. **Through hole:** `solid.hole` with `clearance: "M3"` (ISO 273; `fit: normal` gives 3.4), through both parts.
2. **Head side:** `solid.hole` with `type: counterbore`, `cb_diameter` = head Ø + 0.5–1.0 (M3: 6.0–6.5), `cb_depth` = head height + 0.2–0.5 (M3: 3.2–3.6 on the grid).
3. **Nut side, hex trap:**
   - Sketch `sketch.polygon.circumscribed` with 6 sides around a circle of Ø = flats + 0.3 (M3: 5.8). Across flats = that circle.
   - `solid.extrude` with `operation: cut`, depth = nut height + 0.2–0.5 on the 0.4 grid (M3: 2.8).
   - Keep sharp hex corners.
4. **Side-entry slot (optional):** a rectangle flats + 0.3 wide from the trap to the outside, so the nut slides in.
5. **Sideways holes:** + 0.1–0.2, or teardrop.
6. **Clamped plastic:** add a metal sleeve or big washers so the plastic doesn't creep.
7. **Hardware list:** bolt length = grip + nut + 1–2 threads. Round up to a stock length (M3: 6, 8, 10, 12, 16, 20, 25, 30).
8. Check tool access. A screwdriver or hex key must reach the head; a tunnel longer than about 50 means redesign.

## Print it
- Keep holes vertical where you can.
- Keep one flat of the nut trap parallel to the bed edge.
- A counterbore that prints upside down needs a one-layer bridge (0.4) that the user drills out after.

## Check before done
- [ ] Clearance 3.4 for M3.
- [ ] Counterbore and trap depths on the 0.4 grid.
- [ ] Trap = flats + 0.3.
- [ ] Bolt length and stock size given.
- [ ] Tool access checked.

## Fails → fix
| Problem | Fix |
|---|---|
| Nut won't go into the trap | Too tight or elephant foot: flats + 0.3, chamfer the edge |
| Nut spins in the trap | Trap too big or corners rounded: keep sharp hex corners |
| Bolt slowly loosens | Plastic creeps: metal sleeve or big washers, lock nut |
| Can't reach the head | Check the tool path; a tunnel > ~50 means redesign |

## Pairs well with
- P6 pins.
- P8 glue for big printed frames.
- P11 clamp sockets.
