---
name: frontend-design-craft
description: Procedural craft for designing and building distinctive, beautiful frontend interfaces — visual direction, typography, color systems, layout, motion, and production-quality CSS/React implementation. Use this skill whenever the user asks to build, design, restyle, or "make beautiful/modern/polished" any web page, landing page, dashboard, app UI, component, portfolio, or prototype; asks for a design system, theme, or brand-consistent UI; complains that a design looks generic, bland, or AI-generated; or requests HTML/CSS/React output where visual quality matters at all — even if they never say "design."
---

# Frontend Design Craft

Design like the lead at a small studio whose clients pay for a point of view. The enemy is not ugliness — models rarely produce ugly. The enemy is **the default**: the design any generator would produce for a similar brief. Every engagement follows the same loop: **direction → plan → self-critique → build → self-critique**.

## Workflow selection

| Task | Load |
|---|---|
| New page/app/component from a brief; visual direction; "make it beautiful" | `references/direction-and-planning.md` — always start here for new work |
| Typography choices, pairing, scale, text that looks off | `references/typography.md` |
| Palette construction, spacing, grid, hierarchy problems | `references/color-and-layout.md` |
| Animation, hover states, transitions, "add some life" | `references/motion.md` |
| Writing the actual CSS/React; restyling existing code; debugging visual bugs | `references/implementation.md` |

A full build loads direction-and-planning first, then the others as needed during execution.

## Non-negotiable ground rules

1. **The brief's explicit words always win.** Where the brief pins a direction, follow it exactly. Where it's silent, that freedom is yours — spend it on a *choice*, never a default.
2. **Ground every design in its subject.** If the brief doesn't pin down the subject, pin it yourself: name the subject, the audience, and the page's single job, and state your choice. Distinctive decisions come from the subject's own world — its materials, instruments, vernacular — not from a style library.
3. **Two passes, always.** Pass 1: write a compact design plan (palette as named hex values, type roles, layout concept, one signature element). Pass 2: critique that plan — "would I produce this same plan for any similar brief?" — revise what's generic, *then* code, deriving every value from the plan.
4. **One signature element.** Spend boldness in exactly one place; keep everything around it quiet and disciplined. Before shipping, remove one accessory (Chanel's rule).
5. **Quality floor, unannounced**: responsive to 320px, visible keyboard focus, WCAG AA contrast, `prefers-reduced-motion` respected, real content over lorem ipsum. Never present these as features; they're the floor.
6. **Copy is design material.** Write interface text from the user's side of the screen: plain verbs, sentence case, specific over clever, consistent vocabulary through a flow ("Publish" button → "Published" toast). Errors state what happened and how to fix it; empty states invite action.

## Known defaults to avoid (calibration)

Current AI-generated design clusters into recognizable looks; produce them only if the brief asks:
- Cream background + high-contrast serif + terracotta/clay accent (~#D97757 reads as a Claude tell)
- Near-black background + single acid-green or vermilion accent
- Broadsheet layout: hairline rules, zero radius, dense columns
- Purple-to-blue gradient SaaS hero with floating glassmorphic cards
- Big-number-small-label stat rows; 01/02/03 markers on content that isn't actually a sequence
- Emoji as icons; identical border-radius + shadow on every element

The test isn't "is this look bad" (they're all legitimate for some brief) — it's "did I choose it for *this* brief."

## Self-critique protocol (after building)

Screenshot if the environment allows; otherwise walk the code. Ask, in order: Does the hero state a thesis specific to this subject? Would the palette/type survive the "any-brief test"? Is there exactly one signature? Does spacing follow the scale everywhere (hunt for arbitrary values)? Does it hold at 320px and at 4K? Then remove one thing.
