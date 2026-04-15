# Alpha Vector — Custom Letterform System

_Prepared by: Senior Brand + Type Design. Status: v1 proprietary letterform brief. Downstream: SVG path execution per letter._

This is **not** a production OTF/TTF. It is a **letterform logic** — a set of geometric rules + per-letter specs — that the downstream designer hand-constructs as SVG paths for the wordmark and any letter-based logo mark. Alpha Vector earns a proprietary display face; body copy continues to use Inter and General Sans per `BRAND_CONCEPT.md`.

---

## 1. Design rationale — why a proprietary display face

General Sans is correct for body, documentation, and marketing surfaces. It is **not** distinctive enough to carry the wordmark of a company whose name _is a mathematical promise_. Every infra brand of this calibre carries its own letterform DNA (Stripe's wordmark, Vercel's triangle-forward A, Linear's custom L). Alpha Vector has none. This fixes that.

How it maps to the four pillars:

- **Precision** — a single geometric rule applied to every letter eliminates the humanist "drift" General Sans carries in its terminals. The face is deducible, not drawn.
- **Momentum** — the signature constraint (below) is directional, not symmetric. Every letter leans into the vector.
- **Composure** — one rule, applied without exception. No alternates, no swashes, no weights. The restraint _is_ the design.
- **Foundation** — letters are constructed on a shared cap grid with shared stroke mass. They look like primitives from the same quarry.

---

## 2. The signature constraint

> **Every stroke terminal and every counter-opening in the typeface is cut on a single 23° diagonal, rising from lower-left to upper-right — no flat, rounded, or perpendicular ends exist anywhere in the system.**

One rule. One angle. Every letter obeys it.

### Why 23°

- Not 15° (too subtle — reads as a printing artifact).
- Not 30° or 45° (too decorative — reads as a chamfer, and 45° collides with the Vector Rhombus mark).
- **23°** is the tangent of roughly the golden-ratio-minus-one (`tan⁻¹(0.42)`). It is _just_ past the threshold where the eye registers "this is intentional direction," while staying shy of fashion-geometry territory.

### Why this constraint (pillar fit)

- **Precision:** a single numeric constant governs the whole face. Any letter can be verified with a protractor.
- **Momentum:** the cut always rises to the upper-right — every letter is vectorially biased toward the reading direction. The wordmark literally moves forward.
- **Composure:** the constraint is invisible at a glance and undeniable once seen. No shouting.
- **Foundation:** the 23° facet is the same "cut" mandated by Logo Principle #4. The typeface and the marks are now the same material.

This is the **Vector Cut** — the name of the constraint. Every designer on the project refers to it by that name.

---

## 3. Construction grid

All letters are constructed inside a **64 × 64 unit viewBox** for logo use. Wordmark-set letters use the same proportions.

| Parameter | Value | Notes |
|---|---|---|
| viewBox | `0 0 64 64` | Per-glyph canvas for logo-scale work. |
| Cap height | **28 units** | Letter occupies y = 18 → y = 46 (vertically centered with 18 unit top/bottom margin for wordmark breathing). |
| Baseline | y = 46 | |
| Cap line | y = 18 | |
| x-height | N/A | **Uppercase only.** No lowercase exists in this system. |
| Stroke width | **5.6 units** (cap height ÷ 5) | Applied as the constant stem mass. Horizontals optically corrected to 5.2 units to avoid top-heaviness. |
| Letter advance width | **28 units** standard (same as cap height; 1:1 square-ish cadence) | Narrow letters (I-like stems) = 12 units; wide letters (M, W — not in our set) = 36 units. |
| Side bearings | **4 units left / 4 units right** inside each advance cell | |
| Corner treatment | **Sharp, zero-radius**, _except_ where the 23° Vector Cut applies (all terminals and all counter-openings). No optical rounding. No 2-unit chamfer. | |
| Tracking in wordmark | **−2%** (tight, confident — matches `BRAND_CONCEPT.md` rule) | |
| Overshoot | Curves overshoot baseline/capline by **0.8 units** to optically align with flat-top letters (O, C). |

The 23° Vector Cut is applied **at the terminal**, measured from the notional perpendicular end of the stroke. It consumes the outer 3.5 units of stroke length. The cut direction is always rising left-to-right (↗).

---

## 4. Letterform specifications for A L P H A V E C T O R

Terse specs. Downstream designer constructs each as SVG path inside the 64 × 64 cell. "Vector Cut" below always means the 23° diagonal described in §2.

### A
Isoceles triangular skeleton. The apex is **not** pointed — it is cut flat along a single 23° Vector Cut, making the top of the A a tiny rising facet (≈4 units wide). The crossbar sits at y = 36 (low crossbar for structural weight), cut at 23° on _both_ ends where it meets the legs. The apex cut is the letter's signature moment — the whole face's constraint is readable from this one glyph.

### L
A single vertical stem meeting a single horizontal foot. Top of stem is cut at 23° (Vector Cut). Right end of foot is cut at 23° (Vector Cut, rising). The inner 90° corner stays sharp — the cut is always at the _outer_ terminal. Advance width = 22 units (narrower than standard to balance the open right side).

### P
Vertical stem full cap-height. Bowl occupies upper half (y = 18 → y = 32), closing back into the stem at y = 32. Bowl's inner aperture where it meets the stem at the bottom is cut at 23° — the counter opens slightly to the upper-right, visible as a tiny notch. Top of stem cut at 23°. Bottom of stem cut at 23°.

### H
Two vertical stems, crossbar at y = 32 (true optical centre, 4 units above geometric centre). All four stem terminals cut at 23° (Vector Cut). Crossbar ends are **not** cut — they die flush into the stems. Advance width = 30 units.

### V
Two diagonal strokes meeting at a point at y = 46 (baseline). The meeting point is **not** cut — it is the one permitted sharp apex in the system, because cutting it would produce a flat-bottom V that reads as an incomplete U. Both top terminals cut at 23°, and because the right diagonal is already rising toward 23°-ish, its top cut is nearly horizontal — _accept this_. It is the intended dissonance that proves the rule. Advance width = 32 units.

### E
Three horizontal arms off a single vertical stem. Top stem terminal cut at 23°. Bottom stem terminal cut at 23°. Each of the three arm terminals cut at 23°. Middle arm is **0.75×** the length of top/bottom arms (shortened for optical tension, not decoration). Arms are 5.2 units thick (horizontal-stroke weight).

### C
Open geometric form — a near-circle with a single vertical chord removed on the right side from y = 22 to y = 42. Both terminals of the opening are cut at 23° (Vector Cut), creating two parallel rising facets that frame the aperture. The aperture width is **8 units** — wide enough to be unmistakably a C, narrow enough to hold the counter. Overshoot top and bottom by 0.8 units.

### T
Horizontal cap-arm spanning the full advance width; vertical stem descending from its centre. Both ends of the cap-arm cut at 23°. Bottom of stem cut at 23°. The cap-arm is 5.2 units thick; stem is 5.6 units. The cap-arm's left and right cuts are **mirrored in direction** — left end cut rises ↗, right end cut also rises ↗ (NOT mirrored to ↘). This asymmetry is intentional — it preserves the "all cuts rise left-to-right" rule and gives T a subtle forward lean.

### O
Pure geometric — a rhombus-softened square, not an ellipse. Four rounded-to-sharp corners: each corner is a 23° Vector Cut, **not** a curve. So O is octagonal in construction: four long straight sides + four short 23° cut corners. Each cut corner is 5 units long. This is the letter that most announces the system. Counter is large; stroke is constant 5.6 units.

### R
P's bowl + a diagonal leg descending from the bowl-stem junction (y = 32) to the baseline (y = 46). Leg terminal cut at 23° (Vector Cut). Top of stem cut at 23°. Bottom of stem cut at 23°. The leg's angle is **~38°** from vertical — chosen so its terminal cut remains a clean 23° facet relative to the stroke, not relative to the page. The leg does **not** connect flush to the bowl; it emerges from the stem, leaving a visible 1.5-unit gap between leg-top and bowl-underside. That gap is the R's distinctive tell.

---

## 5. Seven new unique logo directions

These must be _more_ distinctive than existing Directions A–F in `BRAND_CONCEPT.md`. All seven use the Vector Cut (23°) and the construction grid above. All seven pass the anti-pattern list.

### G — **Cut Alpha**
A single uppercase **A** constructed per §4, scaled to fill the logo cell. The entire logo is one letter — but every terminal (apex, both feet, both crossbar ends) displays the 23° Vector Cut. At favicon size the apex cut is the only thing you see, and it is enough. In the color version, the triangular counter beneath the crossbar is filled Vector Blue; the letter body is Obsidian.
**Why more unique than A–F:** Existing Direction A ("Faceted Alpha") uses two triangular _planes_ meeting at a facet — a constructed illustration of an A. This is the _actual typeface A_ used as the mark. The mark and the wordmark are now provably the same object.
**Pass:** Reads as A in under 0.4s. Apex cut visible at 16 px.
**Fail:** If the cut reads as damage or a typo. If it requires the crossbar to be animated/coloured to read.

### H — **Overcut Alpha (apex diacritic)**
The same **A** from §4, but with a **detached 23° facet** floating 3 units above the apex cut — a tiny parallelogram (4 × 1.5 units) set in Vector Blue, acting like an orthographic diacritic that marks the A as "first / leading / alpha." Monochrome version: the diacritic is solid Obsidian.
**Why more unique than A–F:** No Thai/SEA infra brand uses a diacritic mark on a Latin capital. It is culturally literate (alpha = first; the mark is literally an accent of firstness) without being illustrative.
**Pass:** At favicon scale the diacritic must read as _intended_, not as a dust speck. The gap must be exactly 3 units, never less.
**Fail:** If the diacritic is misread as an i-dot, a bullet point, or a notification badge.

### I — **AV Orthographic Ligature**
A true ligature where **A** and **V** share their _entire_ centre diagonal. The A's right leg and the V's left leg are **one single stroke** (not two strokes overlapping). Both outer terminals (A's apex-cut and V's right terminal) carry the 23° Vector Cut. The crossbar of A remains; V has no crossbar. Silhouette is a four-pointed asymmetric star — six vertices total, four of them cut, one sharp (V's baseline apex), one implicit.
**Why more unique than A–F:** Existing Direction C ("AV Interlock") has A and V _sharing an edge_. This direction has them _sharing a stroke_ — one glyph, not two. It is an orthographic event, not a monogram.
**Pass:** Both A and V legible simultaneously. The shared stroke must look _load-bearing_, not coincidental.
**Fail:** Reads as M, W, chevron pattern, or a luxury-fashion monogram.

### J — **Baseline-Inverted V**
A single uppercase **V** — but the baseline of the V is not at y = 46, it is at **y = 18** (the cap line). The letter hangs from the top of the cell, apex pointing down. Both top terminals cut at 23°. The downward apex is sharp. Set in a 64 × 64 cell with the wordmark "ALPHA VECTOR" set in a tight row beneath — the inverted V becomes a downward vector pointing _at_ the wordmark, indicating where to look.
**Why more unique than A–F:** No competitor does a baseline-inverted letterform. It breaks orthographic expectation _just_ enough to be unforgettable, and it gives "Vector" its direction — down, onto the product surface.
**Pass:** Reads as a V on first glance, then as "a V pointing at something" on second glance — in that order.
**Fail:** Reads as a generic chevron or a checkmark. Reads as a play button. Reads as decoration.

### K — **Stencil Alpha**
The **A** from §4, but with a 5-unit-wide **stencil bridge** cut out of both diagonals exactly where they would meet at the apex — the apex plane is isolated, floating, connected to the rest of the A only via the crossbar. Every terminal (including the four stencil cuts) is 23° Vector Cut. Reads as an A under construction, literally composed of its primitive parts.
**Why more unique than A–F:** Stencil letterforms are rare in infra branding (closest: USPS, NASA — industrial, not crypto). Signals "built, not poured." The apex-as-floating-plane directly echoes Logo Principle #4 (the cut).
**Pass:** The floating apex must not look accidentally disconnected. The stencil gaps must be visible at 32 px (may collapse at 16 px — accept this; use direction G as the favicon fallback).
**Fail:** Looks like a damaged A. Looks like military branding.

### L — **Vector Column**
A **vertical stack** of three glyphs at tight tracking: a small 23° parallelogram (5 units), a slim vertical stem (14 units tall, stroke width 5.6, top and bottom cut at 23°), and an open-bottom **V** (apex pointing up, a baseline-inverted V at smaller scale). Read top-to-bottom: _cut / stem / point_ — which is the anatomy of a single letter stroke in our system, shown in pieces. A diagrammatic logo for a company whose name is a diagram.
**Why more unique than A–F:** No letterform at all — it is the _grammar_ of the letterform, stacked. This is the only way a custom-typeface project can produce a logo that is both typographic and non-typographic simultaneously.
**Pass:** Reads as one unified mark, not three stacked glyphs. The cut-stem-point rhythm must feel like one gesture.
**Fail:** Reads as an interface widget, a progress indicator, or a signal-strength icon.

### M — **ALPHA· VECTOR mono-ligature (wordmark-as-mark)**
The full wordmark set per §6, but compressed so tight that the final **R of ALPHA** and the initial **V of VECTOR** share a single 23° facet — the R's leg terminal _is_ the V's left diagonal's top cut. No visible space character between the two words; the lockup becomes one twelve-letter orthographic object. This is both the wordmark and the standalone mark — duplicating as an extreme-wide banner favicon / email signature / letterhead lockup.
**Why more unique than A–F:** Existing Direction E (Wordmark Lock) tilts the V. This direction _fuses_ two words via a single shared facet — something no infra brand has done. It is the purest expression of "the typeface is the brand."
**Pass:** At full length the shared facet must be visible on inspection but invisible at a glance — the reader sees "ALPHA VECTOR," the designer sees the ligature.
**Fail:** Reads as "ALPHAVECTOR" one word. Reads as a typo. Requires color to work.

---

## 6. Wordmark lockup spec

### The canonical form

**`ALPHAVECTOR`** set in the custom letterform, all caps, 28-unit cap height, tracking −2%.

### Spacing between ALPHA and VECTOR

**Not a space character. Not flush. A single dedicated glyph:** the **Vector Bullet** — a **23° parallelogram** measuring 4 × 1.5 units, vertically centred on the cap midline (y = 32), rendered in Vector Blue `#2D5BFF` in the color version and Obsidian `#0B0D12` in monochrome.

- Gap from final R of ALPHA to left edge of bullet: **6 units**.
- Gap from right edge of bullet to left edge of V: **6 units**.
- Total inter-word gap: **~16 units** (roughly 0.6 × cap height).

The bullet is **the only glyph in the system that is not a letter**, and it is also the system's smallest possible expression — it can stand alone as a mobile app dock icon, social profile avatar, or punctuation inside marketing copy ("Alpha · Vector"). It _is_ the Vector Cut, condensed to a glyph.

### Color treatment

- **Default:** All letters Obsidian `#0B0D12`. Vector Bullet `#2D5BFF` (Vector Blue).
- **On dark surfaces:** All letters `#FFFFFF`. Vector Bullet `#4B73FF` (dark-mode Vector Blue per `BRAND_CONCEPT.md`).
- **Monochrome-only contexts:** Bullet takes the letter color. No exceptions.
- **The V is not italicised.** Direction E's tilted V is _retired_ in favour of this bullet. Do not combine.
- **The first A is not coloured.** Do not highlight any single letter — the whole wordmark is one weight, one tone, one system.

### Sizes

- **Minimum wordmark size:** 88 px wide (≈11 px cap height). Below this, use direction G (Cut Alpha) or the Vector Bullet alone.
- **Standard UI header:** 24 px cap height.
- **Hero / print:** any size ≥ 48 px cap height; no maximum.
- **Favicon:** wordmark is **not used**. Use direction G.

---

## 7. What this typeface will NOT do

Hard anti-patterns specific to the letterform system. Any violation requires written justification.

- **No lowercase.** Uppercase-only system.
- **No weights.** One weight (the 5.6-unit stem) exists. No Light, no Black. If you need emphasis, resize — do not reweight.
- **No italics.** Ever. The 23° Vector Cut already carries the directional lean; italicising stacks lean on lean and destroys the constraint.
- **No alternate characters.** One A, one V, one E. No stylistic sets. No swash R. No single-story a (there is no lowercase at all).
- **No ligatures other than direction I (AV) and direction M (R·V bullet bridge).** No æ, no fi, no st.
- **No numerals or punctuation in v1.** If the wordmark needs a number beside it ("Alpha Vector 2026"), set the number in General Sans Semibold. The custom face is strictly the 26-letter reservoir, minus lowercase — in practice, only the 10 letters spelled out in §4 are defined in v1. Other capitals are defined only on demand.
- **No curved strokes.** O is octagonal, not elliptical. C is assembled from straight chord and cut terminals. P's bowl is constructed from four straight segments + four 23° cuts. If you find yourself drawing a Bézier curve, stop.
- **No optical rounding at corners.** Sharp or cut. Never softened.
- **No drop shadows, outlines, or effects.** The letterform is the design. Decoration is forbidden.
- **No variable-font behaviour.** The letters do not animate, morph, or respond to cursor. Any motion happens to the entire wordmark as a rigid body, not to the glyphs internally.
- **No Thai/CJK companion face in v1.** When Thai is needed, set it in **IBM Plex Sans Thai** Medium — proven, free, structurally compatible with the geometric logic of this face. Do not attempt to custom-draw Thai glyphs under the 23° rule; the constraint does not translate and will produce unreadable type.

---

_End of v1 custom letterform brief. Next step: downstream designer executes SVG paths for the 10 letters in §4, the Vector Bullet in §6, and the 7 new logo directions in §5._
