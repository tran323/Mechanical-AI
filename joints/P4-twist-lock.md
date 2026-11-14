# P4 Twist-lock (bayonet)
Family: printed · Comes apart: yes, many times · Extra parts: none · Holding: medium · Best plastic: PETG

## What it is
- Lugs on the cap drop into notches in the ring.
- You push down, then turn: each lug runs along a side slot and locks.
- A small click bump stops it turning back.
- A slight ramp pulls it tight.

## Use when
- Caps and lids you open often
- Quick-release mounts: lens caps, filters, tool heads
- Round parts that must lock at one angle

## Skip when (use instead)
- The lugs would be smaller than 3. They snap off. Use P5 or P2.
- It must take a big pull along its axis. The lugs are small. Use H3 or P5.

## Sizes
No design standard covers printed twist-locks. These come from metal bayonets and printed practice.

| What | Guides | Ender 1.0 (guess) |
|---|---|---|
| Number of lugs | 2 opposite usual · 3–4 for more twist · jar lids 4–6 | 3 |
| Lug size | metal: 1.5–3 pins | ≥ 3 deep × 3 tall · 15–25° of the circle |
| Gap around the lug | 0.1–0.2 (metal) | 0.3–0.5 sideways · 0.4–0.6 up and down |
| Turn angle | 90° usual · 60° on small parts | at most 360° ÷ lugs − lug width |
| Inside slot corners | R 0.3–0.5 or more | R ≥ 0.5 |
| Click bump | 0.3–0.5 high, rounded tip | same |
| Underside of each lug | 45° chamfer: no support | same |
| Ramp in the side slot | no published rule | 2–5° rise, then a dip at the end |
| Ring wall behind the slot | — | ≥ 3.3 |

## Model it in SolidCraft
1. **Ring:** a tube with wall ≥ 3.3, made with `solid.revolve` or an extrude.
2. **Entry notch:**
   - Sketch a rectangle (lug width + 2 × gap) on a plane through the axis.
   - `solid.extrude` it radially through the wall with `operation: cut`.
3. **Side slot:**
   - Sketch the slot's cross-section (lug height + 0.4–0.6 gap, by the lug depth + gap) on the XZ plane at the notch.
   - `solid.revolve` about Z with `angle` = turn angle and `operation: cut`.
   - For the ramp, tilt the slot's top edge 2–5°, or add a small wedge after.
4. **Pattern:** `solid.pattern.circular` the notch and slot features about Z, `count` = lugs.
5. **Cap lugs:**
   - Sketch and extrude a lug at the cap's radius.
   - `solid.chamfer` its underside at 45°.
   - Pattern it the same count.
6. **Click bump:** 0.3–0.5 high, near the end of the slot, with a matching dip.
7. `solid.fillet` the inside slot corners, R ≥ 0.5.
8. **Optional check:** `joint.create` cylindrical (or revolute) between cap and ring with `limits` on the turn angle, then sweep it.

## Print it
- Print the ring and cap with their axis straight up.
- Chamfer the underside of each lug at 45° so it needs no support.

## Check before done
- [ ] Lugs ≥ 3 × 3, with the underside chamfered.
- [ ] Gaps 0.3–0.5 sideways and 0.4–0.6 up and down.
- [ ] The turn angle fits between the lugs.
- [ ] `inspect.interference` finds no overlap when locked.

## Fails → fix
| Problem | Fix |
|---|---|
| A lug snaps off | Too small or lines across it: ≥ 3, chamfer the underside |
| Too tight to turn | Flat lug faces sagged: more up-down gap and the 45° chamfer |
| Turns back by itself | Add the click bump near the slot end |
| Wobbles when locked | Gap too big: add the small ramp so it pulls tight |

## Pairs well with
- P2 for push-on instead of twist.
- P5 for a sealed screw cap.
