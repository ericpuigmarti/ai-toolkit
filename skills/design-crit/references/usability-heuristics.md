# Usability heuristics

The heuristic set and severity scale for visual audit mode and for the UX lens of the blind panel. Using one shared set keeps audits comparable across reviewers. Judge each issue against the audience and core task, not in the abstract.

Tag each issue with the heuristic it breaks. If an issue breaks none of them, check whether it is a taste preference before raising it.

## Heuristics

1. **Visibility of system status.** The interface shows what is happening: loading, saving, progress, success, and failure, in a timely way.
2. **Match with the real world.** Words, concepts, and order follow the audience's language and mental model, not internal jargon.
3. **User control and freedom.** People can undo, go back, cancel, or exit a flow without penalty.
4. **Consistency and standards.** The same thing looks and behaves the same way everywhere, and follows platform and design-system conventions.
5. **Error prevention.** The design removes error-prone conditions, or confirms before a costly action. Constraints, defaults, and inline validation come before error messages.
6. **Recognition over recall.** Options, actions, and context are visible. People do not have to remember information from one screen to the next.
7. **Flexibility and efficiency.** Common tasks are fast for repeat users, and new users are not blocked. Shortcuts, defaults, and prefilled data count here.
8. **Aesthetic and minimal design.** Every element earns its place. Extra content competes with the content that matters.
9. **Error recovery.** Error messages say what went wrong in plain language and how to fix it, and preserve the person's input.
10. **Help and documentation.** Guidance is available at the point of need, short, and task-focused.

## Severity scale

Use the same definitions as the standard critique:

- **Critical:** blocks or seriously risks task completion, safety, comprehension, accessibility, or recovery.
- **Major:** creates substantial friction, ambiguity, inconsistency, or loss of trust.
- **Minor:** creates a localized clarity, consistency, or polish problem without threatening task completion.

An issue that blocks the core task is more severe than one that only affects a secondary task. Do not raise severity because an issue is visually noticeable.

## Scope

These heuristics are about usability. Brand fit, copy standards, and design-system rules come from the product context and the `ux-writing` skill. A visible accessibility risk gets flagged here in usability terms with a pointer to a standards-based audit. A visual inspection is not proof of WCAG conformance.
