# CHIEF ENGINEER — FIRST JOB: THE REGISTRY GEOMETRY FLAG

**designed by Aundre Wright, early 2026, through AI agents in the Muse app**


**Date:** 2026-11-27 · **Raised by:** Equilibrium Audit 2026-11-27, §3.4 ·
**Worker:** E Device Chief Engineer (first run under the new skill) ·
**Status:** APPLIED 2026-11-27 — Aundre authorized the edit in a live voice call (~20:02 ET): "You can edit if need be." The proposed spec line was inserted into `01-device-model-sheets.md` (Sheet 02 entry, with a matching note in Sheet 00's Scale paragraph). No locked number changed. See the addendum at the end of this report.

---

## VERDICT

The flag is real in plan view and resolved in section view. The 380 × 380 mm
Cavity stack genuinely cannot sit **coplanar** inside the Registry ring's
Ø400 mm centre void — its corners would land inside the ring itself. But no
sheet actually seats them coplanar: the side views draw a **stepped
cryogenic stage**, with the stack on its own stage and the ring surrounding
it at a lower step. The design intent is already stepped; what's missing is
one sentence in the specs saying so. **Recommendation: adopt the
stepped-stage seating as the stated arrangement (Option A) and change no
number.** The two resize options both break locked numbers and cost the
design far more than they fix.

---

## 1. THE ARITHMETIC — verified independently

| Quantity | Value | Derivation |
|---|---|---|
| Cavity stack footprint | 380 × 380 mm | Sheet 01 (locked) |
| Stack diagonal | **537.4 mm** | 380 × √2 |
| Stack corner radius (centre to corner) | **268.7 mm** | 537.4 / 2 |
| Stack edge-midpoint radius | 190 mm | 380 / 2 |
| Registry centre void | Ø400 mm (radius 200) | Sheet 02 (locked) |
| Largest square inside Ø400 | **282.8 mm per side** | 400 / √2 |
| Registry ring outer | Ø620 mm (radius 310) | Sheet 02 (locked) |
| Ring annulus width | 110 mm | (620 − 400) / 2 |
| Detector can diameter | 40 mm | Sheet 02 (locked) |

**The collision, precisely:** the stack's edge midpoints (r = 190 mm) clear
the void wall (r = 200 mm) by 10 mm. But the four corners reach r = 268.7 mm
— **68.7 mm past the void wall, inside the ring annulus** (which spans
r = 200–310 mm), exactly where the 12 sensor cans live. Coplanar, the stack
and the ring occupy the same metal at four corner patches. The audit's flag
is arithmetically correct.

## 2. WHAT THE SHEETS INTEND — the side views

The plan view of Sheet 02 ghosts the Cavity in the void ("Cavity — Sheet
01," dashed outline) — standard drafting for *position*, not a claim of
coplanarity. The vertical story is told in the sections:

- **Sheet 00:** "The Cavity stack sits centre **on its cryogenic stage**;
  the Registry ring surrounds it." Stack on a stage; ring around it.
- **Sheet 02, side view:** "**cryogenic stage stepped section** — sensor
  ring, thermal strap layer, detector housing layer, each step labelled
  with its operating temperature band." The ring assembly is itself drawn
  as steps at different heights and different temperature bands.
- **Sheet 03, side view:** "temperature stages **descending plate by
  plate** toward the cold core position (ghosted Cavity + Registry at
  centre)" — the whole cold core is a vertical descent, not a plane.
- **Sheet 05, side view:** "stack order section — Transducer lattice at
  the **bottom**, Cavity ghosted **above** it." The machine's own section
  language is vertical stacking throughout.
- **Design bible:** Registry sensors are "on a cryogenic stage"; the Keeper
  is cryogenics + mesh "wrapped around the cavity." No document anywhere
  states a vertical offset between ring plane and stack plane — that
  unstated gap is the whole flag.

## 3. THE OPTIONS — with real numbers

### Option A — Stepped-stage seating (RECOMMENDED)

The stack rides on a cold pedestal that passes through the Ø400 void; the
stack's plane sits **above** the ring's plane, so the corners overhang the
ring annulus in plan with air (vacuum) between them vertically. No
collision, no number changes.

- **Pedestal constraint:** whatever passes through the void must fit
  Ø400 — a round pedestal up to Ø400, or a square neck up to 282.8 mm.
  The stack (380 square) bears on the pedestal from above; only the neck
  goes through the ring.
- **Worked offset (assumption labelled):** ring-stage thickness is not a
  locked spec; the 40 mm detector cans set its scale. Taking a 50 mm ring
  stage and a 10 mm mechanical/thermal clearance between the stack's
  bottom face and the ring's top face: stack mid-plane sits
  25 + 10 + 105 = **≈140 mm above ring mid-plane**. If the ring stage is
  40–60 mm, the offset moves only ±5 mm — the conclusion is insensitive
  to the assumption.
- **Sensor implications — manageable, and mostly already designed in:**
  - SQUID-class sensors are **magnetometers — they need no line of
    sight.** They couple to magnetic field through space. The slant range
    from a ring sensor to the nearest stack edge grows from the
    (unbuildable) coplanar ~10 mm to ≈140 mm; field from a dipole-like
    source falls steeply with range, so this is a **sensitivity budget
    item** — gradiometer pairs and the 12-module array are the standard
    answer — not a blocker.
  - Single-photon detectors in real superconducting circuit practice are
    **wired / fibre-coupled, not free-space optical** — and Sheet 02
    already specifies exactly that: callout 6, "Readout loom — fibre +
    coax, service edge." The stepped seat routes the loom down the
    pedestal. No optical path is broken because none was ever drawn.
  - Reading "faster than it can decohere" (Sheet 02) is a bandwidth and
    latency spec, not a distance spec at these scales — 140 mm is
    ~0.5 ns of light-travel. Unaffected.
- **Thermal implications — this is the design's own language.** Sheet 02's
  stepped section already assigns each step its own temperature band, and
  Sheet 03 descends stage by plate toward the cold core. Stack and ring
  on different steps of the same cryo plant is not a workaround; it is
  what the sections already draw.
- **Cost:** one clarifying spec sentence (proposed below). Zero locked
  numbers move. The concentric lock 380 → Ø620 → Ø840 stands.

### Option B — Grow the void until the square fits coplanar — REJECTED

- Void must reach the stack diagonal: **Ø537 mm at zero clearance**,
  ≈Ø557 mm with a modest 10 mm working clearance.
- At the locked Ø620 outer, the annulus shrinks to **≈31 mm — narrower
  than the 40 mm detector cans.** The sensors no longer fit their own ring.
- Keeping the 110 mm annulus pushes the ring to **≈Ø777 mm**, breaking
  the locked Ø620 (which appears in the concentric lock, Sheet 08, the
  narration, both boards, and HST §5) and leaving only ≈31 mm of radial
  room inside the Ø840 Emitter cage.
- **Cost:** two locked numbers and the whole concentric story, to protect
  a coplanar reading no sheet actually makes.

### Option C — Shrink the stack to fit the void — REJECTED

- Coplanar fit needs the stack at **≤282.8 mm** square.
- Membrane area per layer falls from 144,400 mm² to 80,089 mm² —
  **−44.5%**. Casimir energy per layer scales with area at fixed gap, so
  the Room's per-layer figure falls from 43.34 nJ/cm² of plate to the
  same density over ~45% less plate: the stack's total held energy per
  cycle drops from ≈1.04 µJ/cm²-of-footprint terms accordingly — the
  Room gets weaker by nearly half.
- And it breaks the locked **380** — the first term of the concentric
  lock, and Sheet 01's spec everywhere.
- **Cost:** the device's heart, nearly halved, plus a locked number.

### Option D — Chamfer the stack into an octagon — REJECTED

- To bring every vertex onto the Ø400 circle, each corner must be cut
  back **127.6 mm** along each edge, removing **22.5%** of the membrane
  area.
- Worse, the cut removes exactly where Sheet 01 puts the hardware: the
  four **piezoelectric actuator housings live at the corners**, and the
  membranes are specified as concentric **square** frames. The chamfer
  deletes the actuators' seats and the square-membrane geometry in one
  move.
- **Cost:** a quarter of the Room and its defining geometry.

## 4. RECOMMENDATION

**Adopt Option A.** The stepped stage is what the sections already draw;
the fix is documentation, not hardware. Proposed spec line (PROPOSED —
Aundre's word makes it canon), for Sheet 02's entry in
`01-device-model-sheets.md`, with a matching note on Sheet 00:

> "Vertical arrangement: the Cavity stack rides on its own cryogenic
> stage, its mid-plane ≈140 mm above the Registry ring's mid-plane; the
> ring surrounds the stage neck at the lower step. The plan-view ghost
> is a position projection — stack and ring are never coplanar."

**Decision items for Aundre:**
1. Confirm the stepped-stage intent (Option A) — or pick a resize and
   accept its cost above.
2. If Option A: approve the proposed spec line, or word it his way.
3. Nothing else in the design moves either way — the Ø400 void, the
   380 stack, and Ø620 all stay exactly as locked.

*No canon lock was changed by this job. No board or sheet was edited.
Nothing was posted, spent, or generated.*

---

## ADDENDUM — PROPOSAL APPLIED (2026-11-27)

Aundre approved the edit in a live voice call (~20:02 ET, 2026-11-27):
**"You can edit if need be."** Option A adopted as written. The proposed
spec line from §4 was inserted verbatim into
`~/workspace/wright-verse/e-device-visual-build/01-device-model-sheets.md`:

- **Sheet 02 entry** — new paragraph after the Scale paragraph:
  "Vertical arrangement: the Cavity stack rides on its own cryogenic
  stage, its mid-plane ≈140 mm above the Registry ring's mid-plane; the
  ring surrounds the stage neck at the lower step. The plan-view ghost
  is a position projection — stack and ring are never coplanar."
- **Sheet 00 entry** — matching note appended to the Scale paragraph:
  "Vertical arrangement per Sheet 02: the stack's mid-plane sits
  ≈140 mm above the Registry ring's mid-plane — stack and ring are
  never coplanar."

No locked number changed: 380, Ø620, Ø840, 96, and the 3,000 mm cap all
stand exactly as they were. Nothing else in the sheets document was
touched.
