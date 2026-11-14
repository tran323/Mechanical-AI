# P12 Magnet pocket
Family: printed · Comes apart: yes, any time · Extra parts: magnets (and glue) · Holding: light · Best plastic: any

## What it is
- A small magnet sits in a printed pocket.
- Parts snap together by magnetism and come apart any time, with no wear.

There are three ways to fit it:
1. **Press-fit:** a snug pocket.
2. **Glued:** a looser pocket with glue.
3. **Sealed inside:** pause the print, drop it in, and print over it. It can't fall out and leaves a clean face, but the skin weakens the pull.

## Use when
- Removable covers and lids
- Tool holders, panels and doors
- Lids that fit only one way (alternate N and S)

## Skip when (use instead)
- It gets hot. Common N-grade magnets weaken above about 80 °C.
- It must hold against a strong pull. Use P1, P4 or H3.

## Sizes
| What | Guides | Ender 1.0 (guess) |
|---|---|---|
| Press-fit pocket | magnet Ø + 0.1–0.15 | + 0.2, test it |
| Glued pocket | magnet Ø + 0.2–0.3 | + 0.3–0.4 |
| Pocket depth | magnet + 0.1–0.2 | round up to whole layers (3 mm magnet → 3.2) |
| Sealed pocket | + 0.2–0.3 wider · + 0.2 deeper | same, depth on whole layers |
| Skin over a sealed magnet | 2–4 layers | 2 layers (0.8) |
| Where to pause | before the first layer that covers the pocket | check it in the G-code once |
| Keep it down during the pause | snug fit or a drop of super glue | same |

## Polarity
- Mark one face of the magnet stack before splitting it, and check each magnet against a marked one.
- Or put a magnet in one part and a steel disc in the other, so polarity doesn't matter.

## Model it in SolidCraft
1. Ask for or assume the magnet size (common: Ø6 × 3, Ø8 × 3, Ø10 × 3). Tell the user which you assumed.
2. **Open pocket:**
   - `solid.hole` with `diameter` = magnet Ø + 0.2 (press) or + 0.3–0.4 (glued).
   - `depth` = magnet thickness rounded up to the 0.4 grid.
3. **Sealed pocket:**
   - Cut the pocket as an inside void: + 0.2–0.3 wider, depth on whole layers, with 0.8 of skin above it.
   - Report the pause height to the user: Z of the pocket top, the layer that starts covering it.
4. Line up pockets on both parts at matching positions. For one-way lids, alternate N and S.

## Print it
- Print with the pocket opening up.
- For a sealed magnet, add a pause at the covering layer in the slicer's layer slider. Test the pause on a small dummy print first.

## Check before done
- [ ] Magnet size stated.
- [ ] Pocket Ø and depth on the 0.4 grid.
- [ ] For sealed pockets, the skin is 0.8 and the pause Z is given to the user.
- [ ] Pockets line up between the parts.

## Fails → fix
| Problem | Fix |
|---|---|
| Magnet jumps onto the nozzle | Pocket too loose: glue it, or make it snugger |
| Paused on the wrong layer | Pause before the covering layer; check the G-code |
| Mating magnets push apart | One is flipped: mark faces, check against a marked magnet |
| Weak hold | Skin too thick: thinner cover or a bigger magnet |

## Pairs well with
- P3 lids.
- P6 pins, to stop the parts sliding off.
