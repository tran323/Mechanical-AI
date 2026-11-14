# P2 Ring snap (annular snap)
Family: printed · Comes apart: with a 30–45° back face (90° stays on) · Extra parts: none · Holding: light–medium · Best plastic: PETG

## What it is
- This is a round snap.
- A lip inside the cap stretches over a bead around the neck, then catches under it.
- The whole ring has to stretch. Slots in the cap skirt turn it into fingers, so it bends instead.

## Use when
- Round caps and lids
- Pen caps, tube end caps, push-on covers
- Battery and sensor caps

## Skip when (use instead)
- The cap is PLA and you open it often. It cracks. Use PETG, add slots, or use P4 or P5.
- The lid is square or very large. Use P3 or P1.

## Sizes
| What | Guides | Ender 1.0 (guess) |
|---|---|---|
| Undercut y, one part stiff | y ≤ ε × d (d = neck Ø) | same |
| Undercut y, both parts flex equally | up to 2 × ε × d | same |
| Example: 30 mm cap opened again | PETG ≤ 0.63 · PLA ≤ 0.36 | PLA is under the print error: add slots or use PETG |
| Lead-in ramp α | 30° (20–35°) | same |
| Back face | 90° stays on · 30–45° pulls off | same |
| Catch that prints as an overhang | ≤ 1 wide; never chamfer it | ≤ 1.1 (1 line) |
| Slots in the skirt | size each finger like a snap arm (P1) | fingers ≥ 2.2 thick |
| Gap under the bead once clicked | small, so the lip is not left bent | 0.4 (1 layer) |

ε is the allowed bend:
- Opened again: PLA 1.2 %, PETG 2.1 %.
- Snapped once: PLA 2.0 %, PETG 3.6 %.

Example: 0.021 × 30 = 0.63.

## Model it in SolidCraft
1. **Neck:**
   - Sketch the half-section on a plane through the axis (XZ): wall, plus the bead with its 30° lead-in and chosen back face.
   - `solid.revolve` 360° about Z.
2. **Cap:**
   - Sketch its half-section with the inner lip matching the bead.
   - Leave a radial gap so the lip sits 0.4 below the bead when clicked.
   - Revolve it.
3. Keep the catch ≤ 1.1 wide if it prints as an overhang. Don't chamfer the catch face.
4. **Slots (needed for PLA, and helpful for deep undercuts):**
   - Sketch one slot rectangle on the skirt and `solid.extrude` with `operation: cut`.
   - `solid.pattern.circular` about Z, 4–8 slots.
   - Each finger must be ≥ 2.2 thick and checked like a P1 arm.
5. Check that y ≤ ε × d for the plastic and use.

## Print it
- Print the neck standing up.
- Print the cap top-down on the bed. The lip prints as a small overhang, so keep it narrow.

## Check before done
- [ ] y ≤ ε × d (or ≤ 2εd if both flex).
- [ ] For PLA caps opened often, there are slots or the plastic is PETG.
- [ ] The catch is ≤ 1.1 wide, with a 0.4 gap under the bead.
- [ ] `inspect.interference` with the cap on finds no overlap.

## Fails → fix
| Problem | Fix |
|---|---|
| Cracks when pushed on | Undercut too deep: smaller y, add slots, or PETG |
| Pops off too easily | Undercut below the print error: go deeper (slots make it safe) or use a 90° back face |
| Lip droops while printing | Keep the catch 1 line wide, or flip the cap |
| Loose after weeks (PLA) | PLA creeps: switch to PETG |

## Pairs well with
- P4 or P5 when it must also be screwed or twisted shut.
