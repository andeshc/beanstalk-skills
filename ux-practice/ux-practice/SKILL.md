---
name: ux-practice
description: Procedural workflows for actually doing UX work — heuristic evaluations, design critiques, usability test planning, accessibility audits, information architecture, personas, and journey maps. Use this skill whenever the user asks to review, critique, evaluate, or improve a screen, flow, app, website, or prototype; plan or script a usability test; audit accessibility; organize navigation, menus, or content structure; create personas or journey maps; or asks "what's wrong with this design" or "how can I make this easier to use" — even if they never say "UX." Also use when reviewing screenshots or UI mockups of any product.
---

# UX Practice

Procedures, rubrics, and templates for performing UX work — not talking about it. Each workflow lives in a reference file; load only what the task needs.

## Workflow selection

| The user wants… | Do this | Load |
|---|---|---|
| A review/critique of a screen, flow, or product ("what's wrong with this?") | Heuristic evaluation or rapid critique | `references/heuristic-eval.md` |
| To test a design with real users, or a test plan/script | Usability test planning | `references/usability-testing.md` |
| Accessibility check, WCAG compliance, "is this accessible?" | Accessibility audit | `references/accessibility-audit.md` |
| To fix navigation, menus, categories, findability, sitemaps | IA methods | `references/ia-methods.md` |
| Personas, journey maps, or research synthesis | Synthesis artifacts | `references/synthesis-artifacts.md` |

Multiple may apply (a full design review = heuristic eval + accessibility audit). Say which you're running and why.

## Universal ground rules (apply to every workflow)

1. **Establish context before judging.** Minimum viable context: who the user is, the top task, the platform, and the stage (concept / prototype / shipped). If missing, ask one question OR state assumptions explicitly at the top of your output — never silently assume.
2. **Severity-rank everything.** Every finding gets one of: **Blocker** (prevents task completion or excludes a user group), **Major** (causes errors or significant friction), **Minor** (slows or mildly confuses), **Polish** (inconsistency, aesthetics). Lead with blockers. Never emit an unranked list of nitpicks.
3. **Cite the principle.** Each finding names its basis: a Nielsen heuristic, a UX law (Fitts, Hick, Jakob, Miller), a WCAG criterion, or "heuristic judgment — worth validating." No naked opinions.
4. **Every finding pairs with a fix.** Problem → why it matters (user + business cost) → concrete recommendation → cheapest way to validate.
5. **End with next steps.** Every deliverable closes with "What to test next" — the 1–3 highest-risk assumptions and the cheapest method to test each.
6. **Screenshots:** describe what you observe before evaluating it, so the human can correct misreadings of the UI.

## Output skeleton (all evaluative workflows)

```
## Context & assumptions
## What's working          (2–4 items; be specific, this builds trust)
## Findings                (severity-ranked table or list)
## Top 3 recommendations   (highest impact-to-effort)
## What to test next
```

## Anti-patterns to refuse or flag

- Dark patterns (confirmshaming, roach motel, forced continuity, disguised ads): don't recommend; if present, log as a **Major** finding with the ethical/regulatory cost and an alternative meeting the same business goal.
- Redesign theater: if the user asks for a visual refresh but findings show a task-flow problem, say so before restyling anything.
- Fabricated data: never invent usage statistics or "research shows" claims without a source.
