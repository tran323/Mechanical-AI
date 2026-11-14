# Joint guide: read this before every CAD design

This guide covers 16 ways to join 3D-printed parts. All sizes are in mm.
- **P1–P12** use only the printed plastic.
- **H1–H4** add hardware: screws, inserts, nuts, bearings.

Each joint has its own file in this folder. The human version, with drawings, is `joint-guide.html`; it uses the same numbers.

## How to use this guide
1. Read this file whenever a design has two or more parts that touch, join, open, move or carry load between them.
2. Answer the 5 questions below, then use the job table to pick 1–2 joints.
3. Open only the files for the joints you picked and follow them:
   - sizes
   - SolidCraft steps
   - print direction
   - checks
4. Tell the user which joint you chose and why, in one line.
5. Numbers in the **Ender** column are first guesses for this printer and are not tested.
   - Say so.
   - Suggest a small test print for any fit that matters (pins and holes in 0.05 steps).

## 5 questions to pick a joint
1. **Must it come apart?**
   - Never: P8 glue, P1 with a 90° back face, P9 or P10 (they stay joined but move).
   - Rarely: P1, H1.
   - Often: P3, P4, P5, P12, H2, H3.
2. **Must it move?**
   - Swings: P9, P10.
   - Swivels any way: P11.
   - Slides: P7.
   - Turns under load or for years: H4.
3. **How much load?**
   - Light: any P joint.
   - Medium: P4, P5, P7, H1.
   - Real load, pull or shaking: H3, or H2.
4. **Are extra parts allowed?**
   - No: P1–P11.
   - Yes: H1–H4 (screws, inserts, nuts, bearings) or P12 (magnets).
5. **What shape is it?**
   - Round: P2, P4, P5.
   - Box lid: P1, P3.
   - Bigger than the bed: split it, join the pieces with P7 or P8, and line them up with P6.

## Pick by job
| Job | Joints (first choice first) |
|---|---|
| Lid or cover that clicks shut | P1, P3 |
| Round cap that pushes on | P2 |
| Cap that twists on | P4, P5 |
| Join pieces of a print too big for the bed | P7, P8, P6 |
| Line two parts up | P6, P7 |
| Door or flap that swings | P9, P10 |
| Joint that swivels and holds a pose | P11 |
| Comes off easily, again and again | P12, P3, P4 |
| Screw it together | H1 (rarely opened), H2 (opened often), H3 (load) |
| Spins on a shaft | H4 |

## All 16 at a glance
| ID | Joint | Comes apart? | Extra parts | Holding* | Good for | File |
|---|---|---|---|---|---|---|
| P1 | Snap-fit (cantilever hook) | only with a 30–45° back face | none | light | lids, covers, battery doors | P1-snap-fit.md |
| P2 | Ring snap | with a 30–45° back face | none | light–medium | round caps, pen caps, tube ends | P2-ring-snap.md |
| P3 | Flex-fit lid | yes, many times | none | light–medium | box lids that fit even when the printer is off | P3-flex-fit-lid.md |
| P4 | Twist-lock (bayonet) | yes, many times | none | medium | quarter-turn caps, quick-release mounts | P4-twist-lock.md |
| P5 | Printed thread | yes, many times | none | medium | jar lids, big screw caps (≥ Ø20) | P5-printed-thread.md |
| P6 | Pin & hole | yes (glue to make it permanent) | none | lines parts up, weak pull | lining up halves | P6-pin-hole.md |
| P7 | Dovetail & T-slot | slides out the way it went in | none | medium; strong glued | sliding lids, joining big prints | P7-dovetail-t-slot.md |
| P8 | Glue joint | no | glue | strong | big prints made in pieces | P8-glue-joint.md |
| P9 | Print-in-place hinge | no, it swings | none | light | box lids, flip covers | P9-print-in-place-hinge.md |
| P10 | Living hinge | no, it bends | none | light | flip-top caps, clips (not PLA) | P10-living-hinge.md |
| P11 | Ball-and-socket | yes | none | light; holds a pose | poseable arms, phone and camera mounts | P11-ball-socket.md |
| P12 | Magnet pocket | yes, any time | magnets (+ glue) | light | removable covers, tool holders | P12-magnet-pocket.md |
| H1 | Self-tap screw | a few times | screw | medium | quick builds you rarely open | H1-self-tap-screw.md |
| H2 | Heat-set insert | many times | insert, screw, soldering iron | strong | cases you open often | H2-heat-set-insert.md |
| H3 | Nut + bolt | many times | bolt, nut | strongest | brackets, frames, loaded parts | H3-nut-bolt.md |
| H4 | Bearing + shaft | yes, and it turns | ball bearing, steel rod | turns under load | wheels, pulleys, rollers, knobs | H4-bearing-shaft.md |

\* The holding ranking is a rough judgment for printed parts, not a test result.

## Printer defaults (use these unless the user says otherwise)
- **Printer:** Creality Ender-3 V3 SE, PETG or PLA.
  - 1.0 mm nozzle, 1.1 mm lines, 0.4 mm layers (first layer 0.44).
  - Bed 220 × 220 × 250. Keep parts ≤ 215 × 215 × 245, or split them (see P7 and P8).
- **Widths:** draw walls, ribs and arms in 1.1 steps: 2.2, 3.3, 4.4.
  - Minimum 2.2 (2 lines).
  - A single 1.1 line works only for thin fins and springs.
  - Working walls: 3.3.
- **Heights:** draw heights on the 0.4 grid.
  - A gap in Z needs at least 1 layer (0.4).
  - Use 2 layers (0.8) if it must stay open.
- **Overhangs and holes:**
  - Overhangs ≤ 45° from vertical.
  - Chamfer downward-facing edges, don't fillet them.
  - Sideways round holes get a teardrop. Bridges ≤ 10.
  - Holes print small; the fat nozzle makes small holes smaller still.
- **Bottom edge:** chamfer the bottom outside edge 0.4 against elephant foot.
- **Strength:** layers are the weak direction.
  - Springy arms, hooks, fins and lugs lie flat in XY so they bend along the lines.
  - Never let them stand up in Z.

## Fits: gap per side
| Fit | Guides (0.4 nozzle) | Ender 1.0 (guess) | Use for |
|---|---|---|---|
| Press | 0–0.1 | avoid on round parts | A rigid round press fit fails on FDM, because the allowed squeeze is smaller than the print error. Use crush ribs, a cross pin, a diamond peg or glue. |
| Snug | 0.1–0.15 | 0.15–0.2 | locating pins, magnets |
| Sliding | 0.15–0.25 | 0.3 | dovetails, lids, keys |
| Free / turning | 0.25–0.4 | 0.4–0.5 | turning parts, loose hinges |
| Print-in-place | ≥ 0.3 | 0.5 (test 0.4–0.6) | parts printed already joined |

## Allowed bend ε (strain) for parts that flex
| Case | PLA | PETG |
|---|---|---|
| Snap opened again and again | 1.2 % | 2.1 % |
| Snapped once, never opened | 2.0 % | 3.6 % |
| Stays bent the whole time (lid fins) | 0.5 % | 1 % |

- PLA creeps: it slowly gives way if left bent or loaded for weeks. Use PETG for anything springy or clamped.
- For PLA, halve the bend.

## Rules every joint shares
1. Draw the clearance into the CAD geometry: model size = nominal ± gap. Never rely on the slicer.
2. Put a fillet ≥ 0.6 × thickness wherever a part bends. Sharp inside corners crack.
3. Chamfer every lead-in where parts slide together (0.8–1.2 on this nozzle).
4. Small threads (under about Ø20 on this nozzle) don't print well. Use H2 or H3 instead.
5. Make mating parts separate bodies or components, and check them in the assembled position:
   - `inspect.interference`: there should be no overlap, except grip that is meant to be there (P3 fins, P11 pose fit).
   - `inspect.clearance`: gaps should match the fit table.
6. For parts that move, add `joint.create`:
   - revolute for P9 and H4
   - slider for P7
   - ball for P11
   - cylindrical, with limits, for P4 and P5

   Then sweep the motion to check that nothing collides.
7. Before calling it done, list for the user:
   - the joint
   - its key sizes
   - the print direction
   - any Ender guesses that need a test print

## SolidCraft commands that help
- **Snaps and bosses:**
  - `plastic.snap_fit`: arm, width, thickness, catch depth and length.
  - `plastic.boss`: diameter, height, hole, fillet and gusset ribs.
  - `plastic.lip`: lip or groove on a shelled box rim.
- **Holes:** `solid.hole` makes simple, counterbore, countersink, `clearance: "M3"` (ISO 273) and tapped holes.
- **Threads:**
  - `solid.coil` with a custom section sketch makes 45° printable threads.
  - `solid.thread` makes ISO 60° threads, which are poor to print. Avoid it for printed threads.
- **Body shape:**
  - `solid.revolve`, which with `angle` and `operation: cut` gives slots that go part of the way round.
  - `solid.extrude` with `taper` (draft).
  - `solid.shell`, `solid.fillet`, `solid.chamfer`.
- **Repeats:** `solid.pattern.circular` and `solid.pattern.rectangular` repeat lugs, slots, ribs and pockets.
- **Big prints:** `solid.split_body` cuts a big print into pieces.
- **Checks:** `inspect.interference`, `inspect.clearance` and `joint.create` (with `limits`).

## Where the numbers come from
- **Guides:**
  - Covestro/Bayer snap-fit guide
  - ISO 286 and 273 (in `mech-design-rules.md`)
  - static74/3dp-compliant-mechanisms (built on Slant 3D, Prusa KB and UF Makerspace tests)
  - matteo/3d-print-design-skill
  - m-esm/3d-print-modeling
  - Hubs, Fictiv, Protolabs and Formlabs design guides
  - Prusa KB
- **Practitioner write-ups (less certain):** threads, ball joints, magnets, bayonets.
- **Untested:** the Ender column and the holding ranking are untested guesses.
