# Information Architecture Methods

## Symptom → method

| Symptom | Method |
|---|---|
| "Users can't find X" / support tickets asking where things are | Tree test the current structure first (diagnose), then card sort (redesign) |
| Designing categories/navigation from scratch | Open card sort → synthesize → closed card sort or tree test to validate |
| Two navigation proposals to choose between | Comparative tree test |
| Users click the wrong thing first | First-click test |
| Labels in dispute ("Settings" vs "Preferences" vs "Account") | Free-listing / label expectation test, or tree test variants |

## Card sorting

- **Open sort** (users create + name groups): for discovering mental models. 15–20 participants for stable patterns; 30–60 cards; card names must not share leading words (biases grouping).
- **Closed sort** (predefined categories): for validating a proposed scheme.
- **Synthesis**: build a similarity matrix (how often each pair of cards co-grouped); look for stable clusters (>60% co-occurrence), stragglers (cards that scatter — these need renaming or duplication in two categories), and user-generated category names (often better labels than internal ones).

## Tree testing

- Strip all visual design: test the hierarchy as a plain text tree.
- 8–10 findability tasks phrased in user language, never using tree labels verbatim.
- Metrics: **success** (found correct node), **directness** (no backtracking), **first-click correctness** (strongest predictor of final success), time.
- Benchmarks: >80% success = healthy branch; <60% = restructure; high success with low directness = labels ambiguous at intermediate levels.
- Diagnose failures by path: where did wrong-path users diverge? That node's label is the suspect.

## Structural principles

- **Polyhierarchy is allowed**: an item may live in two categories if the sort data supports it; cross-link rather than forcing one "correct" home.
- **Breadth vs depth**: prefer broader-and-shallower (2–3 levels) over deep nesting; each added level compounds error probability. But don't exceed what a scannable menu supports (~7±2 top-level items for primary nav is a guideline, not law — test it).
- **Organize by user task/mental model, never by org chart or database schema.** If nav categories match internal team names, log it as a finding.
- **Labels**: front-load the distinguishing word ("Invoice settings," not "Settings for invoices"); prefer concrete nouns and verbs over branded or clever names; consistency of grammatical form within a level.
- **Navigation ≠ IA**: the tree is the structure; nav, search, filters, and cross-links are complementary access routes. Findability problems are sometimes search problems — check search logs (top queries with no clicks = missing or mislabeled content).

## Deliverables

- **Sitemap**: proposed tree with per-node rationale for anything moved/renamed, annotated with sort/tree-test evidence.
- **Navigation spec**: level-by-level labels, cross-links, and what appears in global vs contextual nav.
- Always close with: which branches are still low-confidence and the cheapest validation (usually an unmoderated tree test, n≈30).
