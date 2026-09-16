# Heuristic Evaluation & Rapid Critique

## When to use which

- **Full heuristic evaluation**: whole product/flow, formal deliverable, or the user says "audit"/"evaluate."
- **Rapid critique**: single screen or component, conversational context, or iteration feedback. Same rules, compressed output (skip the per-heuristic walk; jump to findings).

## Procedure (full evaluation)

1. **Frame it.** Record: primary persona, top 1–3 tasks, platform, and constraints. If evaluating screenshots, list the screens in the order a user would encounter them.
2. **Walk the task, not the screens.** Trace each top task step by step. At each step ask: does the user know what to do next (gulf of execution)? Do they know it worked (gulf of evaluation)?
3. **Sweep the 10 heuristics** (checklist below). Log every violation with location, heuristic, severity, and evidence.
4. **De-duplicate and rank.** Merge findings sharing a root cause. Rank by severity, then frequency of the affected task.
5. **Write up** using the output skeleton in SKILL.md. Target 5–15 findings; more than 20 means you're logging symptoms, not causes.

## Nielsen's 10 — operational checklist

For each, the question to actually ask:

1. **Visibility of system status** — After every action, is there feedback within ~1s? Are long operations showing progress? Is current location/state always visible?
2. **Match with the real world** — Is the language the user's, not the org chart's? (No "sync token expired" to end users.) Do metaphors and icons match user mental models?
3. **User control & freedom** — Can every action be undone or exited? Is there a clear emergency exit from flows (cancel, back, escape)? Multi-step flows: can users go back without losing input?
4. **Consistency & standards** — Same action = same word/icon/placement everywhere? Does it follow platform conventions (Jakob's Law: users expect your site to work like the ones they already use)?
5. **Error prevention** — Are destructive actions guarded (confirm, undo, or delay)? Are error-prone conditions removed (disabled states, constraints, smart defaults) rather than merely warned about?
6. **Recognition over recall** — Is anything the user must remember across screens? (Log as finding: state the item and the screens.) Are options visible rather than memorized?
7. **Flexibility & efficiency** — Accelerators for experts (shortcuts, recents, bulk actions) without complicating the novice path?
8. **Aesthetic & minimalist design** — Does every element on the screen serve the top task? What can be removed with zero task impact? (Name candidates.)
9. **Error recovery** — Are error messages in plain language, stating what happened + how to fix it, near the point of error? Do they preserve user input?
10. **Help & documentation** — Is help contextual (inline hints, empty states) rather than a manual? Do empty states teach?

## Supplementary laws (cite when relevant)

- **Fitts's Law** — small/distant targets on frequent actions are a finding; touch targets <44px are a finding.
- **Hick's Law** — long undifferentiated option lists on decision points; recommend grouping/progressive disclosure.
- **Miller / working memory** — >4±1 items to hold across a task boundary.
- **Peak–end rule** — audit the flow's worst moment and its ending; those dominate remembered experience.

## Finding format

```
[SEVERITY] Short title
Where: screen/step
Heuristic: #N name (or law)
What happens: observed behavior, user's-eye view
Cost: what it does to task success / errors / trust / support load
Fix: concrete change (smallest change that resolves it first; the ideal second)
Validate: cheapest test (e.g., 5-user task test, analytics funnel check, A/B)
```

## Severity calibration examples

- **Blocker**: submit button unreachable by keyboard; error wipes a completed form; user cannot find how to pay.
- **Major**: no feedback after save (users double-submit); jargon labels on primary nav; destructive delete with no undo/confirm.
- **Minor**: inconsistent button casing; redundant confirmation on non-destructive action.
- **Polish**: spacing inconsistencies; icon style drift.

## Rapid critique compression

For a single screen: Context line → 2–3 things working → top 5 findings max in the finding format (one line each is fine) → one "test next." Resist completeness; rank ruthlessly.
