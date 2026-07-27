---
name: delight
description: Identify and design earned moments of personality, polish, surprise, and emotional resonance in digital products without weakening usability, accessibility, trust, or performance. Use when improving product polish; exploring microinteractions, motion, celebratory states, empty states, onboarding, loading, recovery, or brand expression; reviewing whether an interface feels memorable; or deciding where delight is appropriate and how to implement or measure it.
---

# Delight

Improve an already coherent experience by adding restrained, context-appropriate moments that help users feel oriented, capable, recognized, or pleasantly surprised. Treat reliability, speed, clarity, and recovery as the first layer of delight.

## Establish the context

Determine from the product or request:

- Audience and core task
- Emotional state at the moment
- Brand personality and acceptable range of expression
- Frequency of use and repeated exposure
- Domain sensitivity and consequences of error
- Platform, accessibility, performance, and implementation constraints

Ask one compact question only when missing context would materially change what is appropriate. Otherwise state assumptions and continue.

Do not add expressive delight to compensate for confusing flows, poor content, slow performance, or missing feedback. Recommend fixing those foundations first.

## Find earned moments

Look for moments where expression supports the user's experience:

- Meaningful completion or progress
- First successful use or mastery
- Milestones that reflect real effort
- Helpful anticipation or a saved step
- Empty states that orient and motivate
- Waiting states where honest progress or useful content reduces uncertainty
- Recoverable errors where calm, empathetic guidance helps
- Optional discovery that rewards curiosity without hiding essential features
- Small tactile feedback that makes an interaction feel responsive

Prefer one or two high-value moments over personality on every surface.

## Apply a context filter

Use expression freely only when it matches the moment and brand.

Be cautious in onboarding, empty states, repeated confirmations, waiting, and recoverable errors. Keep the user's task primary.

Avoid jokes, celebration, surprise motion, ambiguous copy, or gamification during:

- Safety, medical, financial, legal, privacy, or security decisions
- Destructive, irreversible, or high-consequence actions
- Consent, authentication failure, payment failure, or loss of work
- Urgent situations or errors that block the core task
- Moments where users may be distressed, excluded, or uncertain about consequences

In sensitive contexts, warmth, clarity, calm feedback, and a strong recovery path are often the appropriate form of delight.

## Generate concepts

Consider multiple mechanisms before choosing one:

- Interaction polish: responsive states, spatial continuity, satisfying direct manipulation
- Motion: transitions that explain change, progress, hierarchy, or completion
- Content: concise voice, recognition, or encouragement grounded in the user's actual action
- Visual expression: illustration, color, icon behavior, or subtle environmental variation
- Helpful surprise: a shortcut, remembered preference, smart default, preview, or undo
- Sensory feedback: sound or haptics when platform conventions, consent, and user settings support them
- Progressive discovery: optional details that reward repeat use without obscuring functionality

Avoid generic confetti, novelty cursors, canned jokes, random animation, fake progress, manipulative streaks, and loading entertainment that distracts from an avoidable delay.

## Evaluate each concept

Assess:

1. User value: does it improve orientation, confidence, recognition, efficiency, or emotional tone?
2. Context fit: is it appropriate for the task, audience, culture, and brand?
3. Repetition: will it remain acceptable after the hundredth exposure?
4. Control: can users skip, mute, dismiss, or reduce it when appropriate?
5. Accessibility: does it work with reduced motion, keyboard use, screen readers, zoom, contrast needs, and cognitive differences?
6. Performance: is the benefit worth the loading, runtime, and maintenance cost?
7. Integrity: does it accurately reflect system state and avoid coercion or false urgency?

Reject a concept when expression is more noticeable than the user's progress.

## Recommend delight

For each worthwhile opportunity, provide:

- Moment: where it occurs and what the user is doing or feeling
- Purpose: the experience outcome it should improve
- Concept: the proposed behavior, content, or visual treatment
- Restraint: duration, frequency, and conditions for showing it
- Fallback: reduced-motion, muted, low-performance, or unsupported-platform behavior
- Risk: what could make it annoying, inappropriate, misleading, or inaccessible
- Validation: how to test whether it helps

Rank recommendations by expected user value relative to implementation and maintenance cost. Include a `Do not add delight here` section when restraint is an important part of the recommendation.

## Implementation guidance

- Preserve immediate response to the user's action; never delay core functionality for animation.
- Use motion to explain state change. Keep incidental motion brief and interruptible.
- Respect `prefers-reduced-motion` and provide a non-motion equivalent for important feedback.
- Respect system sound and haptic settings. Never autoplay persistent or unexpected audio.
- Keep semantic labels and alternative text functional. Do not place jokes or hidden content in accessibility metadata.
- Maintain keyboard, focus, screen-reader, zoom, contrast, and touch-target behavior.
- Use the product's existing technology and motion system when possible. Add a library only when the benefit justifies its weight and maintenance.
- Do not use randomized variation where consistency, localization, support, or auditability matters.

## Validate the result

Test the complete task, not only the delightful moment:

- Can users complete the task as quickly and reliably as before?
- Is the system state clear without the expressive treatment?
- Does the experience remain appropriate after repeated use?
- Do reduced-motion and muted experiences retain equivalent meaning?
- Does performance remain within the product's target?
- Do qualitative reactions and behavioral signals support the intended outcome?

Treat screenshots shared, smiles observed, or positive comments as signals, not proof. Check for annoyance, confusion, abandonment, repeated dismissal, and accessibility regressions as well.

## Boundaries

- Do not hide required information in an easter egg or hover-only interaction.
- Do not gamify behavior that should remain voluntary or intrinsically motivated.
- Do not make errors cute at the expense of diagnosis and recovery.
- Do not use celebration to disguise an incomplete, risky, or unsuccessful outcome.
- Do not assume a technique is delightful because it is fashionable.
