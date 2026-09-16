# Implementation

## Tokens first, always

Translate the design plan into CSS custom properties before any component code. Every color, font, radius, shadow, and spacing value in the codebase references a token — zero raw hex or arbitrary px in components.

```css
:root {
  --ink: #1a1d16;  --paper: #faf8f2;  --accent: #b34a2e;
  --muted: #d8d4c8; --wash: #f1ede2;
  --font-display: "…", serif;  --font-body: "…", system-ui, sans-serif;
  --step--1: 0.833rem; --step-0: 1rem; --step-1: 1.25rem; /* …modular scale */
  --space-1: 4px; --space-2: 8px; /* …scale */
  --radius: 8px;
  --shadow-1: 0 8px 30px rgb(26 29 22 / 0.08);
  --ease-out-expo: cubic-bezier(0.16, 1, 0.3, 1);
}
```

Dark theme = redefine tokens under `[data-theme="dark"]` or `prefers-color-scheme`; components never change.

## CSS architecture pitfalls (frequent generation bugs)

- **Specificity collisions**: type selectors (`section`, `h2`) fighting class selectors over margins/paddings — margins get silently cancelled. Rule: layout spacing lives on layout classes only; use `.flow > * + *  { margin-top: var(--space-4) }` (owl selector) for rhythm instead of per-element margins.
- Margin collapsing surprises between sections — prefer parent `gap` (flex/grid) over child margins.
- `100vh` on mobile (browser chrome) — use `100dvh` or `min-height: 100svh`.
- Forgetting `box-sizing: border-box` reset; images without `max-width: 100%; height: auto; display: block`.
- Fixed pixel heights on text containers — content will overflow at 200% zoom or long translations. Let content size containers.
- Horizontal overflow from full-bleed tricks — check `body { overflow-x }` isn't hiding a bug; find the culprit instead.
- Tailwind: keep the plan's tokens in `theme.extend` (or `@theme` in v4) and use those utilities; ad-hoc `text-[13px]`/`#hex` arbitrary values reintroduce the orphan-value problem. Core-utilities-only environments (e.g., CDN/artifact contexts): no arbitrary values at all — verify the environment before relying on them.

## React/component notes

- One component per pattern; variants via props mapping to token-based classes — never inline style overrides sprinkled at call sites.
- Extract the section anatomy (eyebrow/heading/body/evidence) as a component so rhythm stays consistent.
- Images: explicit `width`/`height` or `aspect-ratio` to prevent layout shift; lazy-load below the fold.
- State styling: build hover, focus-visible, active, disabled, loading, empty, and error states for every interactive component at build time — retrofitting them is where inconsistency enters. `:focus-visible` ring uses the accent at ≥3:1 contrast, offset 2px.

## Responsive discipline

- Author mobile-first; the desktop composition is an enhancement.
- Breakpoints follow the content (where the layout breaks), not device names; usually 2–3 are enough.
- At each breakpoint check: line lengths (still 45–75ch), hero type (clamp ends), tap targets ≥44px, table/grid strategies (cards or scroll containers, chosen deliberately).
- Test 320px, 768px, 1440px, and one 4K/ultrawide pass (max-width containers earn their keep here).

## Build-time review loop

After first render (screenshot if possible; otherwise read the DOM/code):
1. Token audit: grep for raw hex/px in components — fix leaks.
2. Rhythm audit: any adjacent spacings within one scale step of each other that should be identical? Make them identical.
3. The squint test: blur the page (or squint) — does attention land on the hero thesis and the signature? If attention scatters, cut decoration until it doesn't.
4. Break test: 2× the length of every headline and list; empty every optional field; 200% zoom. Nothing should shatter.
5. Remove one accessory. Ship.
