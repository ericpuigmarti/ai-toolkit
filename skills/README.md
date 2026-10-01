# Skills

Skills are reusable capabilities with enough context to perform a task consistently.

Give each skill its own folder:

```text
skills/
└── design-crit/
    ├── SKILL.md
    ├── examples/
    └── references/
```

Copy [`../templates/SKILL.template.md`](../templates/SKILL.template.md) to begin.


## Overlapping skills

`design-crit` is the toolkit's product-neutral critique skill. It overlaps in purpose with the Maple team skill `design-critique` (from the Anthropic skills plugin), which always returns a scored, Maple-specific review. Their descriptions are written so each triggers on different requests:

- `design-crit`: unscored findings by default, blind panel, persona lens, annotated audits, any product.
- `design-critique`: the team-standard scored Maple/Polaris review.

If you want only one to fire, disable the other in your Claude skill settings. Do not edit the team skill.

## Shared context

Facts about a design system (tokens, breakpoints, naming) live in the repo's `context/` folder, not inside each skill. Copy [`../context/design-system-context.template.md`](../context/design-system-context.template.md) to `context/<name>-context.md` and fill it in. Filled files are gitignored. `figma-handoff-check` and `design-crit` read it first.
