# H2 Heat-set insert (brass threaded insert)
Family: hardware · Comes apart: many times · Extra parts: insert, screw, soldering iron · Holding: strong · Best plastic: PETG or PLA

## What it is
- A small brass sleeve with a thread inside and knurls outside.
- A hot soldering iron melts it into a hole that is smaller than the insert.
- The melted plastic flows into the knurls and freezes, so the insert can't turn or pull out.
- You get a metal thread in plastic that survives many openings.

## Use when
- Parts you open often
- Electronics cases and lids
- A firm metal thread where a nut won't fit

## Skip when (use instead)
- The wall can't be at least 2 lines (2.2) thick.
- The user has no soldering iron. Use H3 or H1.
- The hole runs sideways. It is hard to press in straight.

## Sizes
| What | Guides | Ender 1.0 (guess) |
|---|---|---|
| Hole Ø, M2 insert | about 3.2 | check the insert maker's table |
| Hole Ø, M3 insert | 4.0–4.2 | 4.0–4.2, check the table |
| Hole Ø, M4 insert | about 5.6 | check the table |
| Hole Ø, M5 insert | about 6.4 | check the table |
| Hole depth | insert length + 0.5–1 | insert length + 0.8 (2 layers) |
| Wall around the insert | ≥ 1.5–2 | ≥ 2.2 (2 lines) |
| Entry chamfer | small | 0.4 |
| Iron temperature | about the print temperature | same |

Insert sizes vary by maker. Ask the user for the insert's outside Ø and length, or state the size you assumed.

## Model it in SolidCraft
1. **Boss:** `plastic.boss`:
   - `diameter` = hole Ø + 2 × 2.2 (M3: 4.1 + 4.4 ≈ 8.8; round to 8.8 or 9)
   - `hole_diameter` = 4.0–4.2 for M3
   - `hole_depth` = insert length + 0.8
   - `fillet` at the root, and ribs if pushed sideways
   - Or use `solid.hole` in a thick wall.
2. **Chamfer:** `solid.chamfer` the hole mouth 0.4.
3. **Clearance hole:** in the mating part, `solid.hole` with `clearance: "M3"` (3.4), counterbored if the head should sit flush.
4. Check that the screw length = top part + about the insert length, and doesn't bottom out.

## Print it
- Point the hole straight up so the insert can be pressed in from the top.

## Check before done
- [ ] Hole Ø from the insert table (M3: 4.0–4.2).
- [ ] Depth = insert length + 0.8.
- [ ] Wall ≥ 2.2.
- [ ] 0.4 chamfer.
- [ ] The hole is vertical as printed.

## Fails → fix
| Problem | Fix |
|---|---|
| Insert goes in crooked | Vertical hole, insert tip on the iron, press slowly straight down |
| Insert spins or pulls out | Hole too big or wall too thin: check the maker's table |
| Melt bulges out of the bottom | Hole too shallow: add the extra 0.5–1 |
| Plastic heaps around the top | Press slower, add the entry chamfer |

## Pairs well with
- P6 pins.
- H3 where the load is high.
