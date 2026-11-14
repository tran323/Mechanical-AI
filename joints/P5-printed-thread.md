# P5 Printed thread
Family: printed · Comes apart: yes, many times · Extra parts: none · Holding: medium · Best plastic: PETG or PLA

## What it is
- A spiral ridge on the neck screws into a spiral groove in the cap.
- Big and coarse threads print well; small and fine ones fuse into rings.
- Use 45° flanks so each flank prints as a normal 45° overhang.

## Use when
- Jar lids and screw caps
- Big knobs, and printed nuts on printed bolts
- Containers you open often

## Skip when (use instead)
- The thread is smaller than about Ø20 on this nozzle (M6 on a 0.4 nozzle). Use H2 or H3.
- The pitch is fine compared with the 0.4 layers. It fuses.

## Sizes
| What | Guides | Ender 1.0 (guess) |
|---|---|---|
| Smallest thread | about M5–M6 (0.4 nozzle) | about Ø20 |
| Layers per pitch | at least 6–8 | pitch ≥ 2.4–3.2; use 3–4 |
| Thread shape | 45° flanks (90° included) | same |
| Proportions (45° thread) | depth 0.33 P · flat tops and roots 0.17 P | same |
| Gap per side | 0.10–0.20 | PLA 0.3–0.4 · PETG 0.4–0.5 |
| Thread start | 45° chamfer 0.8–1.5 + short plain tip | also cut off the thin first half-turn |
| Turns engaged | bolts 2–2.5 × Ø · jar lids 1–2 turns | same |
| Wall behind the thread | 3–5 perimeters (1.6–2.0) | ≥ 3.3 (3 lines) |

## Ridge section, P = pitch
- The section is a trapezoid sitting on the core: base width 0.83 P, top width 0.17 P, height 0.33 P.
- One pitch = root flat 0.17 P + flank 0.33 P + crest flat 0.17 P + flank 0.33 P.

Other thread shapes print worse:
- ISO 60° leaves a 60° overhang.
- ACME (30° included) leaves a 75° overhang.
- A buttress thread (one flat face) prints well only if the flat face points up.

## Model it in SolidCraft
1. **Neck:** a cylinder at the thread's root diameter, with wall ≥ 3.3 behind the thread.
2. **Ridge:**
   - Sketch the trapezoid on the XZ plane at the root radius.
   - `solid.coil` with `sketch` = that profile, `pitch` = P, `turns` or `height`, `axis: Z`, `operation: join`.
   - Check the result: confirm the radius and that the profile sits on the core.
3. **Cap groove:**
   - Make the same coil with the profile grown by the gap (PETG 0.4–0.5 per side).
   - Coil it at the cap's matching radius with `operation: cut`, or cut with the neck body grown by the gap.
4. **Start:** chamfer the thread start at 45° (0.8–1.5) and cut off the thin first half-turn on both parts.
5. **Avoid `solid.thread`** for printed threads. It makes ISO 60° profiles; keep it for cosmetic marks only.
6. **Optional check:** `joint.screw`, or `joint.create` type `cylindrical`, to check engagement.

## Print it
- Print both parts with the thread axis straight up, so each turn prints as a smooth circle.

## Check before done
- [ ] Ø ≥ 20 and pitch 3–4 (≥ 6 layers per pitch).
- [ ] 45° flanks, depth 0.33 P.
- [ ] Gap per side matches the plastic.
- [ ] Lead-in chamfer added and the first half-turn cut off.
- [ ] Enough turns engaged.

## Fails → fix
| Problem | Fix |
|---|---|
| Fused into plain rings | Pitch too fine: ≥ 6 layers per pitch, or thinner layers |
| Binds, won't screw on | Gap too small: open in 0.05 steps; print a thin test ring first |
| Strips or jumps a turn | Too shallow or wall too thin: more turns, thicker wall |
| Hard to start | Add the 45° chamfer, cut the thin first half-turn |

## Pairs well with
- P4 as a quicker quarter-turn option.
- H2 for small threads.
