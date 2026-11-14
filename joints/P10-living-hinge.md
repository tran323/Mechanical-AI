# P10 Living hinge (flexure strip)
Family: printed · Comes apart: no, it bends · Extra parts: none · Holding: light · Best plastic: PP or TPU; PETG for a few bends; never PLA

## What it is
- One thin strip of plastic joins two thick parts and bends as the hinge.
- There is no pin and no assembly: it prints flat in one piece.
- Printed living hinges last tens to hundreds of bends, not thousands.

## Use when
- Flip-top caps and boxes opened now and then
- Clips, straps and folding parts
- One-piece prints

## Skip when (use instead)
- The part is PLA. It cracks within a few bends. Use P9.
- It must bend thousands of times. Use P9 or H4.

## Sizes
| What | Guides | Ender 1.0 (guess) |
|---|---|---|
| Strip thickness | 0.4–0.6 · at least 2 layers | 0.8 (2 layers), or print the hinge at 0.25–0.3 layers |
| TPU strip thickness | 0.8–1.0 | 0.8–1.2 |
| Strip length L | ≥ 3–5 · for a fold θ round radius R: L = θ ÷ 180 × π × R | ≥ 5 |
| End fillets | R 0.76 (moulded parts) | R ≥ 1 on both sides |
| Print lines | across the fold, one strand running into both sides | same |
| Very long hinge | split into 2+ strips (over about 150) | same |
| How long it lasts | printed: tens to hundreds of bends (one FDM test: 25) | same |
| Make it last longer | flex it while still warm from the printer | same |

## Model it in SolidCraft
1. **Strip:** make the two thick parts and the strip as one body. The strip lies on the bed (Z = 0 to 0.8).
2. Quick way: extrude the full outline, then cut a channel down from the top across the hinge line. Leave 0.8 at the bottom; the channel width is L.
3. **Fillets:** `solid.fillet` both channel bottom edges, R ≥ 1.
4. **Long hinges:** split hinges longer than about 150 into 2+ strips with a gap between.
5. **Tell the user the slicer setting:**
   - Set the top and bottom line direction so lines cross the fold, at 90° to the hinge line.
   - Use a single solid strip with no infill.

## Print it
- Lay it flat with the strip on the bed.
- Set the line direction across the fold.
- Bend it a few times while it is still warm.

## Check before done
- [ ] The plastic is not PLA.
- [ ] Strip 0.8 thick, L ≥ 5.
- [ ] End fillets R ≥ 1.
- [ ] The line-direction note is given to the user.

## Fails → fix
| Problem | Fix |
|---|---|
| Cracks on the first fold | Lines run along the fold: turn the part or set the line direction across it |
| Breaks after a few folds | Too thick or PLA: thinner strip, or PETG, TPU or PP |
| Tears at the ends | Add round fillets where the strip meets the thick parts |
| Too stiff | Longer or thinner strip |

## Pairs well with
- P1 to latch the closed cap.
