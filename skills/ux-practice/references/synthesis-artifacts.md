# Research Synthesis: Personas & Journey Maps

## Ground rule

These artifacts compress *evidence* into a usable form. If no research exists, produce **proto-personas / assumption maps**, label them as assumption-based in the title, and list the assumptions most in need of validation. Never present invented detail as research.

## Affinity mapping (the step before either artifact)

1. Atomize raw input (interview notes, tickets, reviews) into single observations — one fact/quote per note, tagged with participant ID.
2. Cluster bottom-up by meaning, not by predefined category. Name clusters with a full sentence insight ("Users don't trust auto-save because there's no visible confirmation"), not a topic word ("Saving").
3. An insight needs ≥3 independent sources or it's flagged as a single-participant signal.

## Personas

**Purpose test**: a persona earns its existence only if two personas would make *different product decisions*. If all users share goals and context, one persona (or none — just a context statement) is correct. 2–4 is typical; more than 5 means they're segmented by demographics, not behavior.

Segment by **behavior and goals**, never demographics. "Occasional-but-high-stakes user" vs "daily power user" changes design; age rarely does.

Template (one page max):

```
Name + behavioral tagline ("Priya — the delegating approver")
Context: role, environment, frequency of use, device
Goals: what they're trying to achieve (outcomes, not features)
Behaviors: 3–5 observed patterns, each traceable to evidence
Pain points: ranked, with a representative quote each
Trust & ability: tech comfort, domain expertise, accessibility needs
Design implications: 3 bullets — what this persona demands of the product
Evidence base: n interviews / data sources / OR "assumption-based"
```

Skip: stock photos, fictional biography padding (hobbies, pet names) — they add false concreteness and invite stereotyping.

## Journey maps

**Scope first**: one persona × one goal × defined start/end. "The whole customer experience" is not a mappable scope.

Structure (columns = stages, rows = lenses):

```
Stages:        e.g., Trigger → Research → Decide → Onboard → First value → Habit
Rows:
  Actions      what they do (observed)
  Touchpoints  where (channel, screen, human contact)
  Thoughts     representative quotes
  Emotion      curve, annotated at peaks and troughs (peak–end rule: the worst
               moment and the final moment dominate memory — mark both)
  Pain points  severity-ranked
  Opportunities mapped 1:1 to pain points, each with an owner-able action
```

Rules:
- Map the **current state** before any future state; future-state maps of unvalidated ideas are fiction with columns.
- Include the moments *outside* the product (word of mouth, waiting for approval, emails) — that's usually where journeys break.
- The deliverable's punchline is the **moments that matter**: the 2–3 stage transitions where emotion dips and abandonment risk is highest, each paired with its opportunity and a metric to watch.

## Jobs-to-be-done (alternative frame)

When persona thinking stalls (users too heterogeneous), reframe: "When [situation], I want to [motivation], so I can [outcome]." Write 3–7 job statements from the evidence; design for the job, not the demographic.
