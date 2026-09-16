# Accessibility Audit (WCAG 2.2 AA baseline)

## Scope and framing

- Default conformance target: **WCAG 2.2 Level AA**. If the user has legal drivers (ADA, EN 301 549, EAA, RPwD Act in India, Section 508), note that AA is the common benchmark but recommend counsel for compliance claims.
- Accessibility findings use the same severity scale; anything that **excludes a user group entirely** (keyboard-unreachable action, missing form labels, seizure-risk animation) is automatically a **Blocker**.
- Cite criteria by number and name, e.g., "1.4.3 Contrast (Minimum)."

## Audit procedure

1. **Keyboard pass** (catches the most, costs the least): Tab through the entire flow. Every interactive element reachable? Focus visible at all times (2.4.7)? Logical order (2.4.3)? No traps (2.1.2)? Custom widgets operable with Enter/Space/arrows?
2. **Structure pass**: One H1; heading levels don't skip; landmarks/regions present; reading order matches visual order (1.3.2); page titled (2.4.2).
3. **Forms pass**: Every input has a programmatic label (1.3.1, 3.3.2) — placeholder is not a label. Errors identified in text, associated with the field, and suggest a fix (3.3.1, 3.3.3). Required fields marked accessibly.
4. **Visual pass**: Text contrast ≥4.5:1, large text ≥3:1 (1.4.3); UI components/graphics ≥3:1 (1.4.11). Information never conveyed by color alone (1.4.1). Text resizes to 200% without loss (1.4.4). Reflow at 320px width (1.4.10). Touch targets ≥24×24 CSS px (2.5.8 — new in 2.2; recommend 44px for comfort).
5. **Media & imagery pass**: Meaningful images have alt text describing function, not appearance (1.1.1); decorative images have empty alt. Video: captions (1.2.2); prerecorded audio: transcript.
6. **Motion & time pass**: No content flashing >3×/second (2.3.1). Auto-moving content pausable (2.2.2). Session timeouts warn and extend (2.2.1). Animation respects `prefers-reduced-motion`.
7. **Screen-reader spot check** (if tooling available; else flag as untested): announce order, button/link names meaningful out of context (2.4.4), state changes announced (ARIA live regions where content updates without navigation).
8. **WCAG 2.2 additions to remember**: 3.2.6 Consistent Help, 3.3.7 Redundant Entry (don't ask users to re-enter data in the same flow), 3.3.8 Accessible Authentication (no cognitive tests like transcription; allow paste in password fields).

## Reviewing code vs. reviewing screenshots

- **Code**: also check semantic elements over div-soup, ARIA only where native semantics can't do the job ("no ARIA is better than bad ARIA"), `alt`, `label`/`for`, focus management on route changes and modals (focus moves in, is trapped, returns on close).
- **Screenshots only**: contrast, target size, color-only signaling, and visible focus can be assessed; everything programmatic (labels, order, announcements) must be listed as **"requires code/AT verification"** — never assume it passes.

## Finding format

```
[SEVERITY] Title — WCAG N.N.N Criterion Name (Level A/AA)
Where / Who is excluded or harmed (be concrete: "keyboard-only users cannot check out")
Fix / Validate (axe-core or WAVE scan, manual keyboard pass, NVDA/VoiceOver check)
```

## Report extras

- Lead the report with the **exclusion summary**: which user groups currently cannot complete the top task.
- Note that automated scanners catch only ~30–40% of issues; a clean axe scan is necessary, not sufficient.
- Close with a prioritized remediation order: Blockers on the top task → all Level A → remaining AA → best practices.
