# P8 Glue joint (keyed)
Family: printed · Comes apart: no · Extra parts: glue · Holding: strong · Best plastic: any that glues

## What it is
- A key (a tongue or pins) lines the parts up, and glue holds them.
- This is the usual way to join a big print made in pieces.
- Glue needs a gap. Parts squeezed together dry are starved of glue.

## Use when
- Prints too big for the bed, cut into pieces
- Permanent assemblies
- Parts too thin for screws

## Skip when (use instead)
- You need to open it again. Use H2, H3 or P7.
- The plastic barely glues (PP, PE).

## Sizes
| What | Guides | Ender 1.0 (guess) |
|---|---|---|
| Glue line, epoxy | 0.1–0.25 | same |
| Glue line, super glue | ≤ 0.1; gel CA for gaps | same |
| Glue pockets | ≥ 0.9 open · 0.5 deep · 10–20° undercut · 2–3 apart | ≥ 2.2 open · 0.4–0.8 deep · 3–4 apart |
| Groove for extra glue | 0.5–1.0 wide × 0.5 deep | 1.1 wide × 0.4 deep |
| Fill channel | Ø1.5–2 thin CA · Ø2.5–4 epoxy, vent at the far end | same; teardrop if sideways |
| Key gap (tongue or pins) | 0.2–0.3 per side | 0.3 |

## Which glue
| Glue | Works on | Good at | Watch out |
|---|---|---|---|
| Super glue (CA) | PLA, PETG, ABS | fast; thin line (≤ 0.1) | fills gaps badly unless gel; can crack some plastics |
| 2-part epoxy | PLA, PETG, ABS, nylon | strongest; fills 0.1–0.25 | slow to set; mix well |
| Acetone (solvent weld) | ABS, ASA only | melts faces into one | does nothing to PLA or PETG |
| Hot glue | any | quick, removable | weak; needs a relief groove |

## Model it in SolidCraft
1. **Split:** `solid.split_body` with a plane at the seam. Choose a seam that is flat and away from loads and visible faces.
2. **Key:** either way, the key decides how the parts line up, so make it fit only one way.
   - Tongue: P7 profile.
   - Pins: P6, 2 or more.
   - Gap 0.3 per side.
3. **Glue gap:** recess one glue face by the glue line, 0.1–0.25 for epoxy.
4. **Grooves:** 1.1 wide × 0.4 deep near the edge, so extra glue has somewhere to go.
5. **Optional pockets:** ≥ 2.2 open, 0.4–0.8 deep, 3–4 apart. Use `solid.pattern.rectangular`.
6. **Closed joints:**
   - Add a fill channel (Ø2.5–4 for epoxy) from outside to the seam, with a vent hole at the far end.
   - Use a teardrop if the channel runs sideways.

## Print it
- Print both halves with the glue faces flat on the bed or straight up, so they come out flat.
- Clean and lightly sand them before gluing.

## Check before done
- [ ] The key fits only one way, with 0.3 gap.
- [ ] The glue gap suits the chosen glue.
- [ ] There is a groove for extra glue.
- [ ] Each piece fits the bed (≤ 215 × 215 × 245).

## Fails → fix
| Problem | Fix |
|---|---|
| Joint starved of glue | Parts squeezed dry: leave a glue gap, add a groove |
| Pockets printed closed | Opening too small: ≥ 2 lines wide |
| Super glue cracked the part | Use epoxy |
| Halves set crooked | Add a key or pins so they go together only one way |

## Pairs well with
- P7 dovetail.
- P6 pins.
- H3 bolts through the seam for big loads.
