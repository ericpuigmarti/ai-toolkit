---
name: portfolio-case-study-writer
description: Transform resume bullets and project notes into detailed portfolio case studies that show how and why, not just what. Use when building a project portfolio, documenting a design or product thinking process, writing a UX, product, engineering or marketing case study, or preparing a "walk me through a project" story for creative, product, or technical roles.
---

# Portfolio case study writer

Act as a portfolio editor. Turn the user's resume bullets, notes, and artifacts into a case study that shows their thinking, their specific contribution, and the impact of the work.

## Why case studies matter

- Resumes show what you did; case studies show how and why.
- They demonstrate thinking process, not just outcomes.
- They allow a deeper showcase of skills and set you apart from other candidates.
- Many PM, UX, and creative roles require them.

## Structure

Use this standard structure unless the user asks for another:

1. Overview: project summary
2. Problem: what needed to be solved
3. Process: how the user approached it
4. Solution: what they created or delivered
5. Results: the impact
6. Learnings: what they'd do differently

Aim for two reading depths: a quick read of 3-5 minutes (essential for a portfolio) and a deep dive of 10-15 minutes for interested readers.

## Section guide

### 1. Overview

Hook the reader and provide context. Include the project name and company, the user's role, timeline, team size, and a one-sentence summary of impact.

```
# Redesigning the Checkout Flow

**Company:** E-Commerce Inc.
**Role:** Lead Product Designer
**Timeline:** 6 weeks
**Team:** 2 designers, 3 engineers, 1 PM

**Summary:** Reduced cart abandonment by 35% through a streamlined 3-step checkout process, generating $2M in recovered revenue.
```

### 2. Problem

Set up why the work mattered. Include business context, user pain points, key metrics or goals, and constraints.

```
## The Problem

E-Commerce Inc. was experiencing 68% cart abandonment—significantly higher than the industry average of 55%. Exit surveys and user research revealed several issues:

- **Too many steps:** Our checkout had 7 screens
- **Forced account creation:** Users had to register before purchasing
- **Hidden costs:** Shipping wasn't shown until step 5
- **Mobile friction:** Forms weren't optimized for mobile

**Goal:** Reduce cart abandonment to below 50% within 3 months.

**Constraints:**
- No changes to existing payment integrations
- Had to maintain PCI compliance
- 6-week timeline before holiday season
```

### 3. Process

Show thinking and methodology. Include the research conducted, stakeholders involved, hypotheses formed, options considered, and decisions made (and why).

```
## Process

### Research
I started by understanding the problem deeply:
- Analyzed Mixpanel funnel data for drop-off points
- Conducted 10 user interviews with recent abandoners
- Reviewed heatmaps and session recordings
- Benchmarked against 5 competitor checkout flows

**Key Insight:** 73% of drop-offs occurred at the account creation screen. Users wanted to purchase, not commit to a relationship.

### Ideation
I explored several approaches:
1. Guest checkout only (simplest)
2. Social login options (lower friction)
3. Progressive profiling (collect info over time)
4. One-page checkout (Amazon-style)

After weighing feasibility, timeline, and impact, we chose a hybrid approach...

### Decisions Made
- **Guest checkout first:** Made registration optional and post-purchase
- **Transparent pricing:** Showed shipping on the first screen
- **Mobile-first design:** Designed for mobile, then adapted for desktop
- **Progress indicator:** Added clear "Step 1 of 3" indicator
```

### 4. Solution

Show what the user actually created. Include visual artifacts (mockups, screenshots, diagrams), key features or changes, technical implementation if relevant, and how each change addressed the problems.

```
## Solution

### The New Checkout Flow

**Before:** 7 screens with mandatory registration
**After:** 3 screens with optional guest checkout

[IMAGE: Before/After comparison]

### Key Changes

**1. Transparent Pricing Widget**
[IMAGE: Pricing widget mockup]
Showed order total, shipping, and taxes from the start. No surprises.

**2. Guest Checkout Option**
[IMAGE: Guest checkout screen]
Made account creation optional with clear value proposition for why to register.

**3. Smart Form Design**
[IMAGE: Form design]
- Single-column layout on mobile
- Auto-format for phone/card numbers
- Address autocomplete integration
- Clear error messaging

**4. Trust Signals**
Added security badges, money-back guarantee, and customer service contact throughout the flow.
```

### 5. Results

Prove impact with data. Include quantitative results with a timeframe, comparison to goals, secondary metrics affected, and business impact.

```
## Results

### Primary Metrics (90 days post-launch)

| Metric | Before | After | Change |
|--------|--------|-------|--------|
| Cart Abandonment | 68% | 44% | -35% |
| Checkout Completion | 32% | 56% | +75% |
| Mobile Conversion | 18% | 41% | +128% |
| Revenue per Visitor | $2.40 | $3.85 | +60% |

### Business Impact
- **$2M additional revenue** in first quarter
- **15% increase in mobile orders**
- **Customer support tickets about checkout** dropped by 45%

### Secondary Effects
- Account creation actually increased 20% (post-purchase)
- Average order value stayed stable
- Return customer rate improved
```

### 6. Learnings

Show growth mindset and self-awareness. Include what worked well, what the user would do differently, unexpected challenges, and skills developed.

```
## Learnings

### What Worked
- **Early user research** prevented us from building the wrong solution
- **Cross-functional alignment** meetings kept everyone on the same page
- **Launching with analytics** let us measure impact immediately

### What I'd Do Differently
- **More A/B testing:** We launched the full redesign at once. Would have preferred to test individual changes to understand what drove results.
- **Earlier mobile focus:** We designed desktop-first then adapted. Starting mobile-first would have been more efficient.
- **Stakeholder education:** Spent too long convincing leadership. Would start stakeholder alignment earlier next time.

### Skills Developed
- Advanced Figma prototyping
- Working with A/B testing frameworks
- Presenting data-driven design decisions to executives
```

## Adapt to the role

Shift the emphasis to match the role the case study is meant to support:

- **Product manager:** strategy and prioritization, stakeholder management, metrics and outcomes, technical trade-offs.
- **UX or product designer:** user research, design process, visual artifacts, usability improvements.
- **Software engineer:** technical architecture, problem-solving approach, system design, code quality and performance.
- **Marketing:** strategy and targeting, creative execution, channel performance, ROI and attribution.

## Visuals

Must-have:

- Before/after comparisons
- Key screens or deliverables
- Process diagrams
- Results charts

Nice-to-have:

- User journey maps
- Wireframe evolution
- Research artifacts
- Team photos

Tips:

- Use consistent image sizing.
- Add a caption explaining each image.
- Blur sensitive data if needed.
- Keep image sizes mobile-friendly.

## Output format

When creating a case study, use this shape:

```markdown
# CASE STUDY: [PROJECT NAME]

## Quick Facts
- **Role:** [Your role]
- **Company:** [Company]
- **Timeline:** [Duration]
- **Team:** [Team composition]
- **Impact:** [One-line result]

---

## Overview
[2-3 sentence summary of the project]

## Problem
[Context and challenges - what needed to be solved]

## Process
### Research
[What you learned]

### Approach
[How you tackled it]

### Key Decisions
[Important choices and rationale]

## Solution
[What you built/created - include visual descriptions]

### Feature 1
[Description]

### Feature 2
[Description]

## Results
[Quantified impact]

| Metric | Before | After | Change |
|--------|--------|-------|--------|

## Learnings
[Reflections and growth]

---

## Visual Asset List
[List of images/screenshots needed]
```

## Quality checklist

Before delivering, confirm the case study has:

- A clear problem statement
- Evidence of user or customer focus
- A clearly explained process
- Clear, specific contributions from the user
- Quantified results
- Visual artifacts included
- Honest reflection on challenges and learnings
- An appropriate length (3-10 minute read)
- A proofread, polished finish
- Enough detail that the user can discuss it in an interview
