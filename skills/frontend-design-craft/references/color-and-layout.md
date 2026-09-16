# Color & Layout

## Palette construction procedure

1. Start from the subject (direction step 2), not a genre convention. Pull a candidate hue from the subject's world, then design around it.
2. Build 4–6 tokens: `ink` (text), `paper` (background), 1 `accent`, optionally `accent-2`, `muted` (borders/dividers), `wash` (subtle fill). Name them semantically, not by hue.
3. **Tint the neutrals.** Pure #000/#FFF/#F5F5F5 read as unfinished. Cast ink and paper toward the accent's temperature (a warm accent wants warm greys). This one move removes most of the "generated" feel.
4. **60-30-10 discipline**: ~60% paper, ~30% ink/structure, ≤10% accent. The accent appears only where attention should go — if it's everywhere, it's nowhere.
5. Verify contrast: body text ≥4.5:1 on its background, large text and UI borders ≥3:1. Check the accent *on paper* and *ink on accent* (button text) — the second one fails constantly.
6. Dark themes: paper becomes a near-black *with the same cast* (#0E0F0C-style, not #000); reduce accent saturation ~10–20% (saturated colors vibrate on dark); elevation = lighter surface, not heavier shadow.

Use OKLCH when constructing tints/shades programmatically — even lightness steps stay perceptually even, unlike HSL.

## Spacing system

- One scale, geometric-ish: 4, 8, 12, 16, 24, 32, 48, 64, 96, 128. Every margin/padding/gap comes from it. Arbitrary values (13px, 27px) are bugs.
- **Proximity is grouping** (Gestalt): space *within* a group must be visibly smaller than space *between* groups — at least a full scale step, usually two. Most "cluttered" complaints are proximity violations, not density.
- Whitespace is the cheapest signifier of quality. When a section feels cheap, double its vertical padding before touching anything else. Section padding on marketing pages: 96–160px desktop, scaled down ~40–50% on mobile.
- Padding inside a container ≥ gap between its children (containers hug their content; they don't crowd it).

## Grid & composition

- 12-column fluid grid with a max-width (1100–1300px for text-led pages; wider for dashboards) and consistent gutters from the spacing scale.
- Break the grid **once, deliberately** — a full-bleed image, an element crossing a column boundary — as composition, not accident. Symmetric, centered, equal-thirds layouts are the default look; asymmetry (7/5, 8/4 splits) with a clear dominant reads as designed.
- Establish alignment lines and honor them: a ragged left edge across sections is the fastest giveaway of carelessness. Optically align — a circle or triangle must overhang its box slightly to *look* aligned.
- Vertical rhythm: consistent section anatomy (eyebrow → heading → body → evidence) so variation elsewhere reads as intent.

## Depth, borders, texture

- Pick **one** depth language per design: borders-only (flat, engineered), shadows-only (soft, layered), or color-plane separation (wash panels). Mixing all three per card is the generated look.
- Shadows: large blur + low opacity + slight y-offset (`0 8px 30px rgb(0 0 0 / 0.08)`), tinted toward ink's cast, never pure black. Two elevation levels max.
- Border-radius is an identity decision: choose one value system (e.g., 0 / 2px sharp-engineered, or 8px outer with inner radii = outer − padding) and never mix sharp and pill arbitrarily.
- Flat expanses of paper can take quiet texture (grain, faint grid/rules) when the direction calls for it — at 2–4% opacity, and honor reduced-data/perf budgets.
