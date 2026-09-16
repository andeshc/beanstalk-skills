# Direction & Planning

## Step 1 — Interrogate the brief

Extract or decide (state assumptions if deciding): subject, audience, the page's **single job** (one sentence: "get a hiring manager to book a call"), brand constraints, platform, and emotional register (three adjectives max — e.g., "precise, calm, expensive" or "loud, warm, handmade").

## Step 2 — Mine the subject's world

List 5–10 artifacts from the subject's actual domain: a chess product → board coordinates, clock faces, algebraic notation, ivory/ebony; a finance tool → ledger rules, tabular figures, ticker density; a bakery → flour texture, handwritten labels, oven warmth. The signature element, palette, and type personality should trace back to at least one of these. This step is what prevents defaults — defaults come from designing in a vacuum.

## Step 3 — Write the design plan (compact, before any code)

```
DIRECTION: one sentence naming the aesthetic point of view
PALETTE (4–6 named hex):
  ink        #1A1D16   near-black with an olive cast (why: …)
  paper      #FAF8F2   …
  accent     #B34A2E   …
  (each color gets a one-line justification tied to subject or register)
TYPE ROLES:
  display    <characterful face> — used with restraint (hero, section heads)
  body       <complementary face>
  utility    <mono/condensed for captions, data> (only if needed)
LAYOUT CONCEPT: one sentence + rough ASCII wireframe of the hero and one section
SIGNATURE: the single element this page will be remembered by, and why it
           embodies the brief
MOTION STANCE: none / one orchestrated moment / ambient — and where
```

## Step 4 — The any-brief test (critique before building)

Mentally run a *different* brief in the same genre through your plan. If the plan survives unchanged, it's generic — revise the failing axis and note what changed. Common failures: palette chosen by genre ("finance = navy"), display face that's just a heavier weight of the body face, hero that's a headline + subhead + two buttons + screenshot for the fifth project running.

## Hero as thesis

The hero must open with the most characteristic thing in the subject's world — a headline in a distinctive voice, an image, a live demo, an interactive moment, a single striking typographic composition. Choose deliberately. If the best hero *is* headline + CTA, make the headline's content and typesetting do the distinctive work.

## Structure encodes meaning

Eyebrows, numbering, dividers, and labels must state something true about the content. Numbered markers only when order carries information. Section labels should be the content's own vocabulary, not "Features / Benefits / Testimonials" run through a thesaurus.

## Matching complexity to vision

Minimal direction → the craft lives in spacing precision, optical alignment, and type detail; there is nowhere to hide. Maximal direction → commit fully (layered texture, dense composition, elaborate motion); a timid maximalist design reads as clutter. The worst position is the middle.

## Redesigns of existing UI

Diagnose before restyling: is the complaint actually visual, or is it hierarchy/flow (route to ux-practice skill)? Preserve what users have learned (layout landmarks, action placement) unless the brief authorizes breaking it. Inventory the current CSS for an implicit token system before imposing a new one.
