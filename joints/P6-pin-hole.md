# P6 Pin & hole (locating pin, dowel)
Family: printed · Comes apart: yes (glue to make it permanent) · Extra parts: none (glue optional) · Holding: lines parts up, weak pull · Best plastic: PETG or PLA

## What it is
- A peg on one part fits into a hole in the other.
- It sets position and stops parts sliding sideways.
- On its own it holds very little pull.

**Key fact:** a tight round press fit does not work on FDM. The allowed squeeze is smaller than the printer's error. Use a shape that wedges (draft), flexes (cross pin) or gets glued.

## Use when
- Lining up two printed halves before screws or glue
- Stopping parts sliding sideways
- Glued parts (the pin sets the position)

## Skip when (use instead)
- Friction alone must hold the parts. Add H1–H3, P1 or P8 glue.
- A tall, thin pin would stand up in Z. It shears at a layer line. Lay it down, or make it short and fat.

## Sizes
| What | Guides | Ender 1.0 (guess) |
|---|---|---|
| Vertical pin Ø d | ≥ 5 | ≥ 6 |
| Pin height h | ≤ 1.5 × d | same |
| Hole gap, total (not per side) | 0.25 · ABS/ASA/nylon 0.5 | 0.3–0.4 |
| Draft on the pin | 1.5° (1–2°) | same |
| Base fillet | 0.5–1.0 | 1.0 |
| Lead-in chamfer on the hole | 0.5–1.0 | 0.8–1.2 |
| Cross pin ("+") arm thickness | 1.35–2.0 (3–4 lines) | 2.2–3.3 (2–3 lines) |
| Diamond peg (lying sideways) | 6–8 across · 0.15–0.20 per side | 8 across · 0.2–0.25 per side |
| Round hole running sideways | teardrop, + 0.2 for sag | same |

## Pin shapes
- **Round with draft:** wedges in. Good for vertical pins.
- **Cross "+":** the arms flex, so it holds by spring.
- **Diamond or square:** for pins or holes lying sideways, so nothing overhangs past 45°.

## Model it in SolidCraft
1. **Pin:**
   - Sketch a circle (d ≥ 6) on the face.
   - `solid.extrude` with `distance` = h (≤ 1.5d) and `taper` ≈ −1.5° so the tip is smaller.
   - `solid.fillet` the base edge, R 1.0.
2. **Hole:**
   - `solid.hole` with `diameter` = d + 0.3–0.4 (total gap) and `depth` = h + 0.4–0.8, so the pin doesn't bottom out.
   - `solid.chamfer` the hole mouth 0.8–1.2.
3. **Cross pin:** sketch a "+" with 2.2–3.3 arms and extrude.
4. **Sideways:**
   - Sketch a diamond, 8 across, with 0.2–0.25 per side.
   - Or a teardrop for a round hole: a circle plus a 45° point on top.
5. Use 2 pins or more, spread far apart, to stop rotation.
6. Check with `inspect.clearance` that the gap matches. Put a pin and hole on matching sketch points of both parts.

## Print it
- Pins standing up in Z stay short and fat.
- Pins lying sideways use a diamond or square shape.

## Check before done
- [ ] No round press fit.
- [ ] The total gap is 0.3–0.4.
- [ ] The pin is ≤ 1.5d tall, with a base fillet.
- [ ] The hole has a chamfer and extra depth.
- [ ] There are 2+ pins for alignment.

## Fails → fix
| Problem | Fix |
|---|---|
| Vertical pin snaps at the base | Shorter and fatter, fillet the base, or print lying down |
| Too loose | Add draft or widen the cross arms; don't go below 0.25 total gap |
| Cracks the hole | More draft, shorter pin, chamfer the hole mouth |
| Sideways hole comes out oval | Teardrop or diamond hole |

## Pairs well with
- P8 glue
- P7 slides
- H1–H3 screws, where the pins align and the screws hold
