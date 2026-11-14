# P11 Ball-and-socket
Family: printed · Comes apart: yes · Extra parts: none · Holding: light; holds a pose · Best plastic: PETG

## What it is
- A ball on a stem (part B) snaps into a cup (part A).
- The cup wraps past the ball's widest point, so the opening is smaller than the ball and holds it in.
- Slots split the cup into fingers that spread as the ball goes in.
- The gap sets the feel: zero gap holds a pose, a small gap swivels freely.

## Use when
- Poseable arms and figures
- Phone, camera and lamp mounts
- Joints that must tilt in any direction

## Skip when (use instead)
- It must hold a heavy pose. Friction holds little, so add bumps or a clamp screw (H3).
- The socket is PLA with no slits. It cracks.

## Sizes
| What | Guides | Ender 1.0 (guess) |
|---|---|---|
| How far the rim reaches past the middle (undercut) | ≤ ε × d · repeated use: 60 % of that | same |
| Opening | no published rule | ≈ 98 % of d with no slits (PLA) · 90–95 % with 2–4 slits |
| Slits in the cup | 2 thin slits, opposite each other | 2–4, each ≥ 1.1 wide |
| Ball Ø d | ≥ 5 | ≥ 15–20 |
| Cup wall | 1.0–1.8 | 1.1 (1 line) to flex · 2.2 to hold |
| Gap for a free swivel | 0.10–0.15 per side (PLA) | 0.3–0.4 |
| Gap to hold a pose | zero, C-shaped socket | 0 to −0.1 |
| Holding power | friction holds about 15–20 g on a short arm · 8 bumps per turn for more | same |

ε is the allowed bend: PLA 1.2 %, PETG 2.1 % when opened again.

Example, PETG, d = 20:
- undercut ≤ 0.42 per side
- opening ≈ 19.2 (96 %)

## Model it in SolidCraft
1. **Ball:**
   - `solid.sphere` Ø d (≥ 15–20).
   - A stem cylinder, with stem Ø ≤ 0.5 × d so it can tilt.
   - `solid.fillet` the neck.
2. **Socket:**
   - Sketch the C-shaped half-section on XZ: inner radius = d/2 + gap, wall 1.1–2.2, rim reaching past the ball's middle to the chosen opening.
   - `solid.revolve` 360° about the axis.
3. **Slits:**
   - Sketch a thin rectangle (≥ 1.1 wide) through the cup wall and `solid.extrude` it with `operation: cut`.
   - `solid.pattern.circular`, 2–4 slits.
4. **Optional detents:** small bumps inside the cup, about 8 per turn, for more holding.
5. `joint.create` type `ball` between ball and socket centres.
6. `inspect.interference`: an overlap of 0 to −0.1 is fine for a pose fit. With a free fit there should be none.

## Print it
- Print the socket opening up or sideways, so the rim stretches along the print lines.
- Avoid tall fingers standing up in Z.

## Check before done
- [ ] Ball ≥ 15.
- [ ] Opening 90–95 % with slits.
- [ ] Slits ≥ 1.1 wide.
- [ ] The gap matches the brief (free or pose).
- [ ] The socket is PETG or slotted.

## Fails → fix
| Problem | Fix |
|---|---|
| Cup cracks when the ball goes in | No slits, or PLA: add slits or use PETG |
| Ball pops out | Opening too big: rim further past the middle |
| Too floppy to hold a pose | Less gap, or add detent bumps inside the cup |
| Slits fused shut | Narrower than one line: ≥ 1.1 wide |

## Pairs well with
- H3: a bolt-clamped socket for heavy poses.
