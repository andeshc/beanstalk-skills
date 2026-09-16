# Typography

Typography carries most of a page's personality. If budget-of-effort must be rationed, spend it here.

## Pairing procedure

1. Pick the **display face first**, from the direction's register — it should have a personality you can name (severe, warm, engineered, literary). Sources beyond the obvious: search Google Fonts by category *excluding* the first page of popularity; consider variable fonts for weight play.
2. Pick a **body face that recedes**: high x-height, open apertures, quiet personality, real italics. It should share one skeletal trait with the display (similar x-height ratio or width) and contrast in every other way.
3. **Utility face** (mono or condensed) only if the content has data, captions, or code.
4. Never pair two faces that are near-identical (two geometric sans) — contrast or unify, don't almost-match.

Overused-right-now (avoid as unexamined defaults, fine if chosen): Inter-for-everything, Playfair Display, Space Grotesk, DM Sans, Montserrat. A single well-chosen variable font used at extreme weight/width poles often beats a lazy pairing.

## Scale and rhythm — concrete numbers

- Build a modular scale: ratio 1.2 (dense UI/dashboards), 1.25–1.333 (marketing/editorial). Define as tokens; every font-size on the page comes from the scale. Hunt down orphan sizes in review.
- Body: 16–18px web, line-height 1.5–1.7. Headings: line-height tightens as size grows — 1.1 or less at display sizes.
- Display sizes need **negative letter-spacing** (-0.01em to -0.04em, more as size grows); all-caps labels need positive (+0.05 to +0.12em) and a size drop.
- Line length: 45–75 characters for body prose (`max-width: 65ch` is a safe default). Never let text span a full wide viewport.
- Establish a spacing relationship between text blocks: space above a heading ≈ 2× space below it (binds heading to its content).

## Hierarchy without size

Size is the crudest hierarchy tool. Prefer, in order: weight, color (ink at 100% / 70% / 45% opacities of the ink token), case, spacing, and only then size. A page that expresses hierarchy at only two font sizes but four ink strengths looks expensive.

## Detail craft (the difference between good and generated)

- Real quotes (“ ”) and apostrophes ('), en/em dashes, `&shy;` or `text-wrap: balance` on headlines, `text-wrap: pretty` on prose where supported.
- `font-feature-settings`: tabular numbers (`tnum`) for any column of figures; ligatures on for display.
- Optical alignment: bullets and quote marks hang into the margin; icons align to cap-height, not bounding box.
- Load fonts with `font-display: swap` and preload the display face; subset if self-hosting.
- Fluid type for heroes: `font-size: clamp(2.5rem, 1rem + 5vw, 5rem)` pattern — always test both clamp ends.
