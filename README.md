# Beanstalk Skills

A collection of reusable skills for AI coding assistants working on frontend design and user experience. Each skill includes a `SKILL.md` entry point and focused reference guides with workflows, checklists, and templates.

## Available skills

| Skill | Use it for |
| --- | --- |
| [Frontend Design Craft](skills/frontend-design-craft/SKILL.md) | Designing and building interfaces with a clear visual direction, thoughtful typography, color, layout, and motion, plus CSS/React implementation guidance. |
| [UX Practice](skills/ux-practice/SKILL.md) | Heuristic evaluations, design critiques, usability test plans, accessibility audits, information architecture, personas, and journey maps. |

## Getting started

1. Choose a skill from the table above.
2. Point your assistant to that skill's `SKILL.md`, or copy the entire skill directory into the skills location supported by your assistant.
3. Keep the `references/` directory alongside `SKILL.md`; the entry point explains which guides to load for each task.
4. Describe your task, audience, constraints, and desired outcome.

The skill directories to copy are `skills/frontend-design-craft/` and `skills/ux-practice/`.

### Example prompts

For frontend design:

> Use skills/frontend-design-craft/SKILL.md to build a responsive landing page for a neighborhood bakery. The main goal is to drive cake preorders, and the visual direction should feel warm and playful.

For UX review:

> Use skills/ux-practice/SKILL.md to review this checkout flow for first-time mobile shoppers. Rank the findings by severity and suggest concrete fixes and ways to validate them.

## Repository structure

```text
README.md
skills/
├── frontend-design-craft/
│   ├── SKILL.md
│   └── references/
│       ├── direction-and-planning.md
│       ├── typography.md
│       ├── color-and-layout.md
│       ├── motion.md
│       └── implementation.md
└── ux-practice/
    ├── SKILL.md
    └── references/
        ├── heuristic-eval.md
        ├── usability-testing.md
        ├── accessibility-audit.md
        ├── ia-methods.md
        └── synthesis-artifacts.md
```

This repository contains Markdown instructions and reference material. No build step or runtime dependencies are required to read or use them.
