# Usability Test Planning & Scripting

## Method selection

| Situation | Method |
|---|---|
| Early concept / prototype, "will people get this?" | Moderated task test, 5 users, think-aloud |
| Comparing two designs | Between-subjects moderated test or A/B (if live + traffic) |
| Live product, "where do people drop off?" | Analytics funnel first, then moderated test on the drop-off step |
| Navigation/labels in question | Tree test or first-click test (see ia-methods.md) |
| No budget/time for recruiting | Hallway test (5 colleagues *not* on the project) — flag reduced validity |
| Need statistical confidence | Unmoderated remote (Maze/UserTesting-style), n≥20 per condition |

**Five users** find ~80% of usability problems for a given persona/task set (Nielsen). Test 5, fix, retest — never 20 in one round.

## Test plan template

```
# Usability Test Plan: [product/feature]
Goal: the decision this test informs (one sentence)
Hypotheses: 1–3 falsifiable statements ("Users will complete checkout in <2 min without help")
Participants: n, persona criteria, screener questions, exclusions (no teammates/friends of team)
Method: moderated/unmoderated, remote/in-person, prototype fidelity
Tasks: 3–5 (template below)
Metrics:
  - Task success (binary or leveled: unaided / aided / fail)
  - Time on task (if it matters to the goal; else skip)
  - Errors (count + type)
  - SEQ (Single Ease Question, 1–7, after each task)
  - SUS (10-item, after session, if benchmarking)
Logistics: duration ≤60 min, recording + consent, incentive
```

## Task writing rules

- **Scenario, not instruction.** ✅ "You bought a kettle last week and it arrived broken. Sort it out." ❌ "Click Orders, then click Return."
- **Never use the interface's own labels** in the task — that's a giveaway.
- One goal per task; realistic data; order tasks independent or natural-sequence.
- Define success criteria per task *before* the session.

## Moderation script skeleton

```
Intro (5 min): "We're testing the design, not you. There are no wrong answers.
Think aloud — tell me what you're looking at, expecting, feeling. I may stay
quiet; that's normal. You can stop anytime."
Warm-up (2 min): background questions relevant to persona fit.
Tasks (35–40 min): read scenario aloud + hand written copy. Then be silent.
Post-task (each): SEQ + "what was going through your mind at [moment of struggle]?"
Wrap (5 min): "What almost stopped you? If you had a magic wand…?" Thanks + incentive.
```

## Moderator discipline (the hard part)

- **Silence is the tool.** Count to 10 before helping. If they ask "should I click this?" → "What would you do if I weren't here?"
- Never lead: ❌ "Did you find that confusing?" ✅ "What did you expect to happen?"
- Only assist after a task is marked failed — then note "aided."
- Probe behavior, not opinion: what they *did* outranks what they *say they'd do*.

## Analysis & reporting

1. Tabulate per task: success rate, SEQ median, error list.
2. Cluster observed problems by root cause; count how many participants hit each.
3. Severity = frequency × impact on task. 3/5 participants failing a step = Blocker regardless of how minor it looks.
4. Report format: Goal → What we did → Findings (severity-ranked, each with a participant quote or clip timestamp) → Recommendations → What to retest.
5. Distinguish observations ("4/5 missed the link") from inferences ("likely because it reads as body text") — label inferences as such.
