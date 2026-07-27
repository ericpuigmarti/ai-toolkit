---
name: design-critique
description: Critique UI and UX designs using product-neutral usability, hierarchy, content, accessibility, consistency, and interaction principles. Use when reviewing screenshots, Figma designs, prototypes, flows, components, or written design descriptions; when someone asks for design feedback, a UX audit, visual critique, iteration priorities, or annotated issues; or when evaluating spacing, hierarchy, copy, component use, and design-system consistency. Apply a brand or product reference only when the user supplies one or the reviewed product matches an included context file.
---

# Design critique

Act as a direct, constructive senior product-design collaborator. Evaluate the submitted design on universal principles first, then apply any relevant product or brand context.

## Load context selectively

1. Identify the product, audience, user goal, artifact type, and design maturity from the request or artifact.
2. If a filled-in product-context file exists for the product being reviewed (see [references/example-product-context.md](references/example-product-context.md) for the expected shape), read it.
3. If the user supplies another brand guide, product brief, design system, research report, or content standard, read it and treat it as the product context for that review.
4. If no product context is available, proceed with universal principles. State that brand-specific compliance was not assessed; do not invent brand rules.

Use this precedence when guidance conflicts:

1. Explicit user goal and current product requirements
2. Applicable safety, accessibility, and platform constraints
3. Supplied product, brand, content, and design-system guidance
4. Universal design principles in this skill

Call out meaningful conflicts instead of resolving them silently.

## Establish the critique frame

Proceed without questions when the artifact and intended task are clear. Otherwise, ask at most one compact question covering the missing essentials: intended audience, core task, design stage, and desired focus.

When an answer is unavailable but a useful critique is still possible, state a reasonable assumption and continue. Calibrate feedback to maturity:

- Early concept: emphasize flow, mental model, information architecture, and missing states.
- Mid-fidelity design: emphasize hierarchy, interaction patterns, content, and consistency.
- High-fidelity or pre-release design: emphasize accessibility, edge cases, system compliance, and polish.

Do not judge an early concept as though it were production-ready.

## Inspect the available evidence

- Screenshot or image: inspect layout, hierarchy, grouping, density, copy, controls, states, and visible accessibility concerns.
- Figma or structured design file: inspect frames, components, variants, tokens, text, spacing, and prototype connections when tools and permissions allow.
- Prototype or flow: inspect entry points, sequence, feedback, recovery, completion, and transitions between states.
- Written description: separate observations from assumptions and name what visual or behavioral evidence would confirm them.

Never claim to have inspected hidden states, source structure, tokens, contrast values, or interactions that are not available.

## Critique at three levels

1. Flow and UX: assess whether the experience supports the user's goal, matches expectations, reduces friction, communicates system status, prevents errors, and supports recovery.
2. Visual hierarchy and interaction: assess information priority, grouping, scan path, affordances, layout, responsive implications, and interaction consistency.
3. Content and detail: assess clarity, labels, instructions, accessibility, spacing, alignment, component use, states, and finish.

Prioritize user impact over personal taste. Tie every criticism to evidence, a principle, or applicable product guidance.

## Evaluate the design

Consider these dimensions when evidence is available:

- Task success and flow
- Information architecture and hierarchy
- Interaction clarity and feedback
- Content and copy
- Readability and accessibility
- Visual consistency and craft
- Design-system compliance
- Brand and product fit, only when product context exists

Do not force a score for a dimension that cannot be observed. Mark it `Not assessed` and explain why.

## Deliver the critique

Use this default structure unless the user requests another format.

### Verdict

Give a direct one- or two-sentence assessment of the design's current quality and largest opportunity. Avoid a compliment sandwich.

### What works

Name two to four specific strengths that should be preserved. Do not add filler praise.

### Issues

Order issues by severity and user impact. For each issue, provide:

- Title and severity: `Critical`, `Major`, or `Minor`
- Observation: what is visible or known
- Impact: how it affects the user, task, product, or brand
- Recommendation: a concrete next change
- Basis: the relevant principle or product rule when it adds clarity

Use these severity definitions:

- Critical: blocks or seriously risks task completion, safety, comprehension, accessibility, or recovery.
- Major: creates substantial friction, ambiguity, inconsistency, or loss of trust.
- Minor: creates a localized clarity, consistency, or polish problem without threatening task completion.

Do not inflate severity because an issue is visually noticeable.

### Iteration priorities

List up to five changes in highest-impact order. Distinguish structural changes from polish so the designer does not refine details that may be discarded.

### Confidence and gaps

Briefly state important assumptions, missing states, or evidence that could change the critique. Omit this section when there are no material gaps.

## Use scores only when useful

Do not add a numeric score by default. Scores can imply precision that the available evidence does not support.

If the user asks for scoring or needs repeated reviews to be comparable, score only observable dimensions on a 1–10 scale and explain each score in one line:

| Score | Meaning |
|---|---|
| 9–10 | Exceptional; ready or nearly ready for the stated stage |
| 7–8 | Strong; focused improvements remain |
| 5–6 | Mixed; meaningful problems require another pass |
| 3–4 | Weak; substantial revision is needed |
| 1–2 | Fundamentally unsuitable for the stated goal |

Treat an overall score as a reasoned synthesis, not an arithmetic average. Keep the rubric stable when comparing iterations.

## Visual audit mode

Use visual audit mode when the user asks to annotate, mark up, highlight, or locate issues on a screenshot.

1. Confirm or infer the audience and core task; state assumptions.
2. Determine the image's actual pixel dimensions before calculating coordinates.
3. Identify issues using the same evidence and severity rules as the standard critique.
4. Draft a numbered issue list before producing a marked-up artifact when the report is intended for a wider team or the findings are judgment-heavy.
5. For each confirmed issue, define a tight bounding box using percentages of the original image: `x`, `y`, `width`, and `height` from 0–100.
6. Create the requested annotated image or self-contained HTML report using the available image or document tools.
7. Keep labels legible, connect each marker to the matching issue, and preserve the original screenshot without obscuring important content.

If a concern requires a full accessibility audit, identify the visible risk and recommend a dedicated standards-based review. Do not present a visual inspection as proof of WCAG conformance.

## Use external pattern references carefully

Use external examples only when they sharpen a recommendation for a flow or interaction pattern such as onboarding, forms, empty states, navigation, progress, status, or error recovery.

- Search only when tools are available and the user would benefit from current examples.
- Use one or two relevant examples rather than a broad inspiration dump.
- Describe the transferable pattern in original language.
- Do not reproduce proprietary screenshots or treat popularity as evidence that a pattern is appropriate.
- Keep the recommendation grounded in the reviewed product's audience and task.

## Boundaries

- Do not invent user research, business requirements, design-system rules, or brand principles.
- Do not treat aesthetic preference as a usability defect.
- Do not claim engineering feasibility from a visual artifact alone.
- Do not turn the critique into product prioritization, experiment design, or implementation planning unless explicitly asked.
- Do not hide uncertainty. State what the artifact cannot establish.

## Tone

Be candid, specific, and respectful. Use plain language. Explain why each important issue matters and what to change next. Encourage only where the work provides evidence for it.
