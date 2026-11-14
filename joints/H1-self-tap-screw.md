# H1 Self-tap screw (screw into a printed boss)
Family: hardware · Comes apart: a few times · Extra parts: one screw · Holding: medium · Best plastic: PETG

## What it is
- A screw cuts its own thread straight into a printed pilot hole in a boss.
- The top part gets a clearance hole, so the screw pulls it down. The thread bites only in the boss below.
- Gusset ribs stop the boss snapping off when pushed sideways.
- It is quick and cheap, but the plastic thread wears out.

## Use when
- Parts you put together once or rarely open
- Light loads
- Quick test builds

## Skip when (use instead)
- You open it often. Use H2.
- It carries a real load. Use H3.
- The boss would be thinner than 2 lines.

## Sizes
| What | Guides | Ender 1.0 (guess) |
|---|---|---|
| Pilot hole, M2 | 1.7 | 1.7–1.9 |
| Pilot hole, M2.5 | 2.2 | 2.2–2.4 |
| Pilot hole, M3 | 2.5–2.7 | 2.6–2.8 |
| Pilot hole, M4 | 3.4–3.6 | 3.5–3.7 |
| Boss outside Ø | 2–2.5 × d | M3: 7 (2 full lines around a 2.6 pilot) |
| Thread engaged | ≥ 2–2.5 × d | same |
| Clearance hole in the top part (M3) | 3.4 | 3.4–3.6 |
| Gusset ribs | at the boss base if pushed sideways | 2.2 thick |

Screws made for plastic (ST sizes) use a pilot of about 0.8 × size, with a matching boss:

| Screw | Pilot | Boss |
|---|---|---|
| ST2.2 | 1.8 | 5.0 |
| ST2.9 | 2.3 | 6.5 |
| ST3.5 | 2.8 | 8.0 |

Machine-screw pilots on a 1.0 nozzle are a guess. Print a small ladder of holes and try them.

## Model it in SolidCraft
1. **Boss:** `plastic.boss` on the lower part:
   - `position`, `diameter: 7`, `height` (on the 0.4 grid)
   - `hole_diameter: 2.7`, `hole_depth` ≥ 2.5 × d (+ 1 below the screw tip)
   - `fillet` at the root
   - `ribs: 3–4`, `rib_thickness: 2.2` if pushed sideways
2. **Clearance hole:** `solid.hole` in the top part with `clearance: "M3"` (3.4), or `diameter: 3.5`.
   - Add `type: counterbore` or `countersink` for the head if it should sit flush.
3. Line up the boss and hole on the same axis. Use matching sketch points or the same world position.
4. Check that the screw length = top part thickness + 2–2.5 × d engagement, and that it doesn't hit the boss bottom.

## Print it
- Stand the boss up, with the screw axis in Z, so the screw pulls along the layers.

## Check before done
- [ ] Boss Ø 7 for M3 (2 full lines).
- [ ] Pilot 2.6–2.8.
- [ ] Engagement ≥ 2–2.5 × d.
- [ ] Clearance hole 3.4–3.6 in the top part.
- [ ] Gussets if loaded sideways.
- [ ] Screw length stated.

## Fails → fix
| Problem | Fix |
|---|---|
| Boss splits | Walls too thin or pilot too small: 2 full lines of wall, slightly bigger pilot |
| Screw spins, won't tighten | Pilot too big or thread stripped: switch to H2 |
| Boss snaps off | Add gussets and a fillet at the base |
| Thread wears out after a few uses | Normal: use H2 for parts opened often |

## Pairs well with
- P6 pins to line the parts up.
