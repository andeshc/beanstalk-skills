# Motion

## Stance first

Decide the motion stance in the design plan: **none** (precision-minimal directions — then perfect the static craft), **one orchestrated moment** (usually page-load or hero), or **ambient** (subtle continuous atmosphere). One well-built moment lands harder than effects scattered everywhere; scattered scroll-triggered fade-ups on every element is the single strongest "AI-generated" tell.

## Craft numbers

- Durations: micro-interactions 120–200ms; element transitions 200–350ms; orchestrated entrances 400–800ms total. Anything over 1s must be skippable or ambient.
- Easing: never `linear` for UI (reserve for ambient loops). Default `ease-out` for entrances (fast start, settle), `ease-in-out` for state changes. Custom cubic-bezier for the signature moment — e.g., `cubic-bezier(0.16, 1, 0.3, 1)` (expo-out) feels expensive.
- Stagger entrances 40–80ms apart, max ~6 items; beyond that, group.
- Distance: entrance translations 8–24px. 100px fly-ins read as 2015.

## What to animate

- **Only `transform` and `opacity`** for anything frequent (compositor-friendly; no layout thrash). Never animate `width/height/top/left` on interaction paths; for expand/collapse use `grid-template-rows: 0fr → 1fr` or measured transforms.
- Micro-interactions earn their keep on: primary buttons (press scale 0.97–0.98), inputs (focus ring transition), state confirmation (a save that visibly settles). Hover lift + shadow-grow on every card is default filler.
- Continuous/ambient motion (gradients drifting, particles): opacity of effect low, CPU budget lower; pause offscreen via IntersectionObserver.

## Orchestrated moments

A page-load sequence: background/canvas first, then hero display type (often the signature — per-line or per-word reveal, clip-path or mask, not per-letter fade which reads as template), then supporting elements, staggered. Author it as one timeline (CSS animation-delays from tokens, or Web Animations API), not per-element one-offs — coherence is what makes it feel directed.

Scroll-triggered reveals: reserve for content where progressive disclosure means something (a step sequence, a narrative). Trigger at ~20–30% viewport entry, animate once, never re-trigger on scroll-up.

## The floor

```css
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    animation-duration: 0.01ms !important;
    transition-duration: 0.01ms !important;
    scroll-behavior: auto !important;
  }
}
```
Include this (or an equivalent opt-in pattern) in every build with motion. Motion must never gate content: if the animation fails or is disabled, everything is still visible — author end-states as the default, entrances as the enhancement.
