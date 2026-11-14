# P1 Snap-fit (cantilever hook)
Family: printed · Comes apart: only with a 30–45° back face (90° locks for good) · Extra parts: none · Holding: light · Best plastic: PETG

## What it is
- One part has a springy arm with a hook on its end.
- Pushing the parts together, the ramp bends the arm.
- The hook then clicks behind a ledge (undercut) on the other part.
- The back face angle decides if it opens again.

## Use when
- Lids, covers, battery doors
- Clips that need no tools
- Fast assembly of many parts

## Skip when (use instead)
- The part is PLA and stays bent for months. PLA creeps and lets go. Use PETG, or P3.
- The arm would have to stand up in Z. It breaks at a layer line. Turn the part, or use P3, H1 or H2.
- It must carry a real load. Use H1, H2 or H3.

## Sizes
| What | Guides (0.4 nozzle) | Ender 1.0 (guess) |
|---|---|---|
| Root thickness t | 1.8 (4 lines) | 3.3 (3 lines) |
| Tip thickness | ≥ 0.9, about t/2 | ≥ 2.2 (2 lines) |
| Arm width (in Z when printed flat) | ≥ 5–6 | 6.4 (16 layers) |
| Hook depth y (undercut) | 0.8 (0.6–1.2) | 0.8–1.0 |
| Arm length L | formula below | PETG ≥ 14 · PLA ≥ 18 |
| Ramp (lead-in) angle α | 30° (20–35°) | same |
| Back face α′ | 90° locks · 30–45° opens again | same |
| Root fillet | ≥ 0.6 × t | ≈ 2.0 |
| Side gap around the arm | 0.3 | 0.4 |
| Allowed bend ε, opened again | PLA 1.2 % · PETG 2.1 % | same |
| Allowed bend ε, snapped once | PLA 2.0 % · PETG 3.6 % | same |

## Formula
`L = √( y × t ÷ (k × ε) )`
- k = 1.09 if the tip is exactly t/2; otherwise k = 0.67.
- On this printer the tip is 2.2, which is not t/2, so use k = 0.67.

Example for this printer, PETG, opened again:
- t = 3.3, tip 2.2, y = 0.8, ε = 0.021.
- L = √(0.8 × 3.3 ÷ (0.67 × 0.021)) ≈ 14 mm.
- The same arm in PLA (ε = 0.012) needs L ≈ 18.

If L is too long for the part, there are three fixes:
1. Lower y (keep y ≥ gap + 0.6).
2. Switch to PETG.
3. Use a U-shaped (folded) arm.

## Model it in SolidCraft
1. Decide the bed plane first. The arm must lie flat in XY: its bending happens in the XY plane and its width runs up in Z.
2. **Quick way:** `plastic.snap_fit`:
   - Inputs: `position` (on the face), `direction` (out of the face), `hook` (the catch direction), `length` = L, `thickness` = t, `width`, `catch_depth` = y, `catch_length`.
   - Then check the ramp angle and the root. The command makes a plain arm, so add the fillet yourself.
3. **Exact way:**
   - Sketch the arm outline on XY. It tapers from t at the root to the tip thickness, with the hook: 30° ramp, chosen back face.
   - Extrude it up by the width (6.4) with `operation: join`.
4. `solid.fillet` the root edges with R ≈ 2.0, where the arm meets the body.
5. Cut the ledge or window in the mating part:
   - depth = y
   - side gap 0.4 around the arm
   - when latched, leave about 0.2–0.4 behind the hook so the arm is not left bent
6. Keep every hook overhang ≤ 45° as printed.

## Print it
- Lay the arm flat on the bed. Draw its outline in XY and extrude up.
- Keep hook overhangs ≤ 45°.

## Check before done
- [ ] The arm lies in XY (it bends along the layers).
- [ ] L meets the formula for the chosen plastic and use (opened again or once).
- [ ] The root fillet is in place, and the tip is ≥ 2.2.
- [ ] `inspect.interference` with the parts latched finds no overlap.
- [ ] The back face angle matches the brief (opens again, or locks).

## Fails → fix
| Problem | Fix |
|---|---|
| Arm snaps at the root | Add the root fillet, make the arm longer, print it lying flat |
| Won't latch | Hook too shallow: y ≥ gap + 0.6 |
| Too hard to push on | Lower the ramp to 20–25°, round the hook nose |
| Loose after a week (PLA) | Switch to PETG, or halve ε |

## Pairs well with
- P6 pins to line the parts up.
- P3 as the gentler choice when the printer's fit is unknown.
