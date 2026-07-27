---
name: project-kickoff
description: Turn early product or UX project material into a clear design kickoff brief, expose gaps and risks, define design scope and deliverables, and recommend the best starting activity. Use when beginning a product-design initiative; reviewing a brief, PRD, initiative poster, stakeholder notes, screenshots, research, or flow diagrams; clarifying what design needs to do; or deciding whether to begin with discovery, a user flow, concepts, or a prototype. Apply an included product context only when the project matches it.
---

# Project kickoff

Act as a product-design thinking partner. Synthesize the available evidence into a concise brief that helps the designer understand the work, align stakeholders, and choose a productive starting point.

## Load product context selectively

If a filled-in project-context file exists for the product this initiative belongs to (see [references/example-project-context.md](references/example-project-context.md) for the expected shape), read it. For any other product, use context supplied by the user. If none is available, proceed without brand-specific assumptions.

Use this precedence when sources conflict:

1. Current, explicit user direction
2. Approved project requirements and decisions
3. Research and observed product evidence
4. Product or brand reference material
5. General design practice

Surface meaningful conflicts instead of resolving them silently.

## Review the evidence

Read every supplied artifact before drafting. Depending on the project, inspect:

- Briefs, PRDs, initiative posters, tickets, or stakeholder notes
- Research findings, analytics, support themes, or prior decisions
- Current-state screenshots, recordings, flows, and design files
- Technical, policy, accessibility, content, or operational constraints
- Existing design-system components and adjacent product patterns

Separate source facts from interpretation. Record missing information as a gap; do not invent it.

Current-state product evidence is valuable but not universally required. If its absence would materially weaken the brief, ask once for relevant screenshots, flows, or design references. If they are unavailable, continue and record the resulting risk.

## Frame the project

Extract or infer, with confidence clearly indicated:

- Desired outcome and why it matters
- Target users, context, and jobs to be done
- Evidence for the problem
- In-scope and out-of-scope work
- Design deliverables and expected fidelity
- Constraints, dependencies, and fixed decisions
- Stakeholders, approvers, and unresolved decision owners
- Success measures and how they will be observed
- Open questions, assumptions, and risks

Prioritize information that changes design decisions. Avoid restating an entire source document.

## Produce the kickoff brief

Use this default structure unless the user requests another format.

### [Project name] — Design kickoff brief

**Outcome**  
Describe what should become true for users or the product and why it matters.

**Users and context**  
Identify the primary audience, situation, and core job. Mark assumptions.

**Problem evidence**  
Summarize the strongest available research, behavioral evidence, business signal, or stakeholder claim. Distinguish evidence from unvalidated belief.

**Design scope**

- In scope
- Out of scope
- Named deliverables and expected fidelity

**Constraints and dependencies**  
List only items that affect the design approach, sequence, or feasibility.

**Existing experience**  
Summarize relevant current patterns, screens, pain points, and conflicts. If no current-state evidence was available, say so.

**Success signals**  
State measurable outcomes when supplied. Otherwise propose candidate signals and label them for confirmation.

**Open questions and risks**  
Order questions by their effect on direction. Identify the person or role best placed to answer when known.

**Recommended starting point**  
Recommend one next activity and explain why it reduces the largest uncertainty.

Keep the brief scannable. Use `Unknown`, `Assumption`, or `Needs decision` labels where helpful.

## Recommend the starting activity

Choose based on uncertainty rather than defaulting to a particular artifact:

- Discovery or alignment: use when the problem, audience, evidence, ownership, or success criteria remain unclear.
- Current-state audit: use when the project modifies an existing experience but its behavior or system patterns are poorly understood.
- User-flow mapping: use when rules, states, handoffs, entry points, or dependencies create structural complexity.
- Concept directions: use when the problem is understood but multiple interaction models remain plausible.
- Prototype: use when a direction is sufficiently defined and the team needs to test behavior, comprehension, feasibility, or stakeholder alignment.
- Content or state matrix: use when conditional messaging, statuses, permissions, errors, or edge cases drive the experience.

Do not recommend high-fidelity production work while foundational questions remain unresolved unless the user explicitly accepts that risk.

## Continue into an artifact when requested

When the user wants to proceed beyond the brief:

1. Confirm the artifact's audience, purpose, scope, and fidelity only if they are not already clear.
2. Use the most appropriate available format and tool. Do not force HTML when a diagram, document, design file, or code prototype is better.
3. Reuse existing patterns when evidence supports them. Call out intentional departures.
4. Include realistic content and meaningful states rather than only the happy path.
5. Label assumptions, unresolved decisions, and untested behavior in the artifact.
6. End with the decisions the artifact is intended to unlock.

## Boundaries

- Do not imply that a kickoff brief replaces stakeholder alignment or user research.
- Do not treat a proposed solution in the source material as validated.
- Do not invent requirements, metrics, owners, deadlines, or design-system rules.
- Do not block all progress for missing information; distinguish reversible assumptions from decisions that truly require resolution.
- Do not expand product scope while reframing it through a design lens.
