# P3 Flex-fit lid (fins or spring arm)
Family: printed · Comes apart: yes, many times · Extra parts: none · Holding: light–medium · Best plastic: PETG

## What it is
- The lid sits loose where it lines up (a plug with a 0.4 gap).
- It grips with thin springy fins, or a side spring arm, that press into the box wall.
- The fins bend to take up the print error, so it fits even when the printer is a bit off.

## Use when
- Boxes with removable lids
- Lids printed on another printer or in another plastic
- Plugs and inserts that sit in an opening

## Skip when (use instead)
- The lid must seal. Fins leave gaps. Use P5 with a gasket.
- The box wall is thinner than 2. The fins need something to press on.

## Sizes
| What | Guides | Ender 1.0 (guess) |
|---|---|---|
| Gap where the lid locates | 0.3 per side | 0.4 |
| Fin press into the wall | 0.3 per side | 0.3–0.4 |
| Fin angle to the wall | 30–45° | same |
| Fin thickness t | 0.86 (2 thin lines) | 1.1 (1 line) |
| Fin length L | PLA ≥ 13.5 · PETG ≥ 9.5 | PLA ≥ 15 · PETG ≥ 11 |
| Relief gap under the fins | 0.3 (0.3–0.5) | 0.5 (more than one 0.4 layer) |
| Side-spring arm | 22.5 long × 2.5 thick, 2.5 slot, R1 corners | 2.2 thick, ≥ 16 long |
| Bump on the arm | Ø1.6–2, 0.3–0.5 proud, ¾ along the arm | same, with a dimple in the box |
| Box wall | ≥ 2 (2.4–3 comfortable) | ≥ 3.3 (3 lines) |

## Formula (fin length)
`L = √( 1.5 × t × (δ ÷ cos φ) ÷ ε )`
- δ = fin press + 0.2 for print error.
- φ = fin angle to the wall.
- ε = 0.5 % for PLA, 1 % for PETG. These are low because the fins stay bent while the lid is on.

## Model it in SolidCraft
1. **Box:** `solid.shell`, wall ≥ 3.3.
2. **Lid:** a flange plate plus a locating plug, offset inward 0.4 per side from the box's inner wall.
3. **Fins:**
   - Sketch them in XY on the plug edge: thin fins at 30–45° to the wall, length L, thickness 1.1.
   - Their tips reach 0.3–0.4 past the box wall line. This overlap is the grip.
   - Extrude them up.
4. **Relief:** leave a relief gap ≥ 0.5 between the fins and the flange (cut a groove under them) so they can't fuse to it.
5. **Side-arm alternative:**
   - Cut a slot to free a 2.2-thick arm, ≥ 16 long, in the plug side, with R1 corners.
   - Add a Ø1.6–2 bump, 0.3–0.5 proud, ¾ along the arm.
   - Cut a matching dimple in the box wall.
6. `inspect.interference`: the fins or bump overlapping the box wall by 0.3–0.4 is intended. Nothing else may overlap.

## Print it
- Print the lid flange down on the bed. Fins and arms keep their outline in XY.
- Check the first fin layer in the sliced preview, to make sure the relief gap survived.

## Check before done
- [ ] The fins are 1.1 thick and long enough by the formula.
- [ ] The relief gap is ≥ 0.5, more than one layer.
- [ ] The locating gap is 0.4 per side.
- [ ] The only intended overlap is the fin or bump grip.

## Fails → fix
| Problem | Fix |
|---|---|
| Fins fused to the flange | Relief gap under one layer: make it bigger and check the sliced layer |
| Lid loosens over weeks (PLA) | PLA creeps: use PETG, or thinner, longer fins |
| Spring arm snapped | Printed standing up or too thick: keep it in the layer plane |
| Rough flash at fin corners | Trim with a knife; chamfer the tops of the corner blocks |

## Pairs well with
- P12 magnets for a lid that drops on.
- P1 for a lid that must latch.
