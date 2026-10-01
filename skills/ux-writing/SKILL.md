---
name: ux-writing
description: Maple's single source of truth for product and UX copy — voice, grammar/mechanics, UI text patterns, tone-by-context, and approved terminology. Use this whenever writing or editing any copy that will appear in the Maple product (buttons, labels, error messages, empty states, form fields, notifications, onboarding, in-app messaging) or when reviewing/critiquing existing UI strings for consistency. Also use when a term's product-facing name is unclear (e.g. "visit" vs "consult", "practitioner" vs "provider") — check the terminology reference before writing copy that names a Maple concept. Always consult this skill before generating final in-product copy, even for short strings like button labels or toasts.
---

# Maple UX Writing

This is the one place to check before writing copy that ships in the Maple product. It consolidates brand voice, grammar/mechanics, UI text patterns, and approved terminology so copy decisions don't get re-litigated or drift between designers, PMs, and engineers.

**Scope: English copy only.** This skill's mechanics (Oxford comma, contractions, Canadian spelling) and voice guidance apply to EN strings. It does not cover French translation — that's a separate skill/process. If a string is going into FR, flag it early (see the self-check below) rather than assuming EN rules or layout carry over.

**Before writing product copy:** check terminology first (below and `references/terms.md`) — using the wrong noun for a Maple concept is the most common and most visible mistake. Then apply voice + mechanics. Then check the pattern for the specific UI element you're writing.

## Output format

Regardless of the source — a screenshot, a Figma file, or strings pulled from a code repo — review output follows the same shape: **flag, suggestion, light rationale.** Don't silently rewrite copy in place unless asked to; default to a review the person can act on.

For each string with an issue:
- **Flag** — the string as-is, and where it lives (screen/frame name, or `file:line` for a repo).
- **Suggestion** — the fixed version.
- **Rationale** — one line: which rule it broke (voice, mechanics, a specific pattern, or a terminology mismatch) and why it matters here. Keep this short — it's context for the fix, not a re-explanation of the whole skill.

Example:
> **Flag:** "Your prescription is being filled." (confirmation screen)
> **Suggestion:** "We're filling your prescription."
> **Rationale:** Passive voice — mechanics calls for active, always.

Check terminology and mechanics first (objective, rule-based) before voice/tone calls (judgment-based) — that ordering keeps the rationale honest about what's a hard rule versus a stylistic nudge. Only flag things that actually break a documented rule; don't invent preferences the skill doesn't state. If two rules conflict — e.g. correct terminology reads awkwardly in a specific sentence — terminology accuracy wins; rephrase around it rather than swapping the term. If a string is FR-bound and space-constrained, add that as its own flag per the self-check below, even if the EN copy itself is otherwise clean.

Strings with no issues don't need a line — silence on a screen/file means it passed.

## Voice

Maple's brand voice is **"You got this"** — upbeat, confident, and clear, without ever tipping into hype or corporate-speak.

| We are | We are not |
|---|---|
| Enthusiastic | Frantic |
| Confident | Cocky |
| Leading | Forceful |
| Clear | Sterile |
| Optimistic | Unrealistic |
| Human, real talk | Folksy, corporate jargon |

Five things this voice does:
1. **Upbeat and optimistic** — see the reader's potential with contagious confidence.
2. **Motivate without pressure** — stay alongside them, encourage, don't push.
3. **Lead with enthusiasm** — celebrate highs, steady the lows.
4. **Know the way** — speak like someone who's been through this before, so guidance feels earned, not generic.
5. **Keep it clear** — explain things simply enough to act on.

This voice is constant across every surface. What changes by surface is **tone** — see "Tone by context" and "Point of view by tier" below. The same product should never sound like two different companies depending on whether you're reading a push notification or an inline error, but it's also fine — expected — for an inline error to sound quieter than a re-engagement email.

**Context always wins.** Patient-facing copy is casual and conversational. Business/government/provider audiences can skew slightly more formal — never cold or stiff. Know the brief, understand the moment, adapt.

## Point of view by tier

There's one point-of-view rule (below), but how much of the full brand voice shows up depends on what kind of copy it is. This isn't a separate rulebook — it's the same voice at different volumes.

**Pronoun rules (apply everywhere):**
- "We" when speaking for Maple
- "You" when addressing the reader
- Avoid "I" unless quoting someone
- Use "Maple" only when introducing the company or adding clarity

**Low tier — functional/system UI** (toasts, snackbars, inline errors, field labels, settings copy): drafted fast, lightweight tone check. In practice this copy skips "we" almost entirely, and often skips pronouns altogether — it's stating a fact or giving a direct instruction.
- "Email is required."
- "Password must be at least 8 characters."
- "You've successfully signed out."
- "There's an issue with your health card number. Please check it and try again."

Note "you" still shows up for direct address — it's "we" specifically that drops out here. Voice still applies (never cold, never blaming) but restrained — see the Frustrated/Confused rows in Tone by context.

**Higher tier — relationship-oriented touchpoints** (push/email notifications, longer nudges, net-new experiences, anything critical or emotionally weighted): full Brand/Clinical review, fuller voice including "we" framing.
- "We'd love to see you at your visit, so get started when you can... our team is always here for you. Warm regards, The Maple Team"

If you're unsure which tier a piece of copy falls into: short, single-purpose, appears at the moment of doing a task → low tier. Longer, relationship-building, or high-stakes (cancellations, health information, first-run experiences) → higher tier, and worth a second look from brand/clinical rather than drafting solo.

## Grammar & mechanics

Clean, consistent, Canadian.

**Contractions:** always in. "We're here for you 24/7," not "We are here for you 24/7."

**Active voice:** go active, always. "We deliver care in minutes" not "Care is delivered in minutes."

**Spelling:** Canadian English always (favour, colour, centre). "Practise" as a verb, "practice" as a noun. Plain language beats jargon.

**Punctuation**
- **Colon** — lists only. "He addressed three topics: diversity, inclusion and mental health."
- **Commas** — where you'd take a breath; **no Oxford comma**. "fruits, vegetables and whole grains," not "fruits, vegetables, and whole grains."
- **Periods** — skip in headlines and CTAs unless making a point.
- **Dashes** — hyphen for compound words ("high-risk levels"). Em dash — no spaces before or after — for asides ("Access medical care online within minutes — anytime, anywhere.").
- **Exclamation marks** — avoid in all instances.
- **Ellipses** — only inside quotes to show a pause. Never for suspense in regular copy.
- **Parentheses** — sparingly; em dashes usually do the job better. Fine for abbreviations: "urinary tract infection (UTI)."
- **Ampersands** — avoid unless space demands it.

**Capitalization**
- Sentence case for titles.
- Proper nouns when official (Maple, Canada), job titles when official but not when general (Dr. Jenkins, Head of Cardiology — not "the head of cardiology" capitalized).
- Diseases lowercase unless a proper name is involved (Parkinson's disease, COVID-19).
- Race, nationality, language terms are capitalized (Francophone, Arabic).

**Numbers**
- Spell out one to nine; numerals for 10+. Spell out numbers that start a sentence.
- Ordinals: spell out first–ninth; numerals for 10th+.
- Percentages: "%" not "percent."
- Decimals: whole numbers by default ($25, not $25.00; 50%, not 50.0%) — keep the decimal only if it's actually part of the price/percentage (50.5%).

**Formatting**
- Bullets for three or more items; no periods unless a bullet has more than one sentence; capitalize the first word of each bullet.
- Avoid italics, underline, and stacking bold/caps.
- One space between sentences. Left-align body text.
- Dates: "July 22, 2025" or "Saturday, July 22." Time: "8am, 8:30pm, 7am to midnight" (add EST if needed). Money: "$5, $99.99, CAD $10." Addresses: spell out street types in full. Phone: "416-555-1234." Temps: "25°C." Weights/volumes: "5g / 5mg," "5L / 5mL." File types uppercase: JPG, PDF, HTML.

## UI text patterns

Apply these patterns for common interface elements. Voice and tone still govern — these are structural, not a substitute for the rules above.

**Titles** — noun phrases, sentence case. Orient the user to where they are. "Account settings," "Your library."

**Buttons and links** — active imperative verb + object, sentence case. `[Verb] [object]`. "Save changes," "View details." Avoid generic labels ("OK," "Submit," "Click here") — specificity does double duty for accessibility (screen readers need context) and clarity.

**Error messages** — pattern: `[What failed]. [Why/context]. [What to do].` Never blame the user, never leave a dead end.
- Validation (inline): "Email must include @." "Password must be at least 8 characters."
- System (modal/banner): "Couldn't save changes. Connection lost. Reconnect and try again."
- Blocking (full-screen): "Subscription expired. Your account is paused. Renew subscription to restore access."
- Permission: lead with the benefit — "Get notified when orders ship. Enable notifications."
- Avoid: raw error codes, blame language ("invalid input"), robotic phrasing ("an error has occurred"), vague causes ("something went wrong").

**Success messages** — past tense, specific. "Changes saved," "Profile updated."

**Empty states** — explain why it's empty + a CTA to populate. "No messages yet. Start a conversation to connect with your team."

**Form fields** — labels are clear noun phrases ("Email address," not "Email"), always visible (never placeholder-only). Instructions appear before input, are specific ("Password must be at least 8 characters," not "Enter valid password").

**Notifications** — verb-first title + contextual description. Low-tier ones stay factual; relationship-building ones can carry fuller voice (see Point of view by tier).

## Tone by context

Voice stays constant; tone adapts to what the user is going through. This is where "context always wins" gets concrete.

| User state | Tone | Example |
|---|---|---|
| Frustrated (errors, failures) | Empathetic, solution-focused, no blame | "Payment failed. Your card was declined. Try a different payment method." |
| Confused (first use, complex features) | Patient, explanatory, break into steps | "Connect your bank to see spending insights. We'll guide you through it." |
| Confident (routine tasks) | Efficient, minimal, quick confirmation | "Saved" |
| Cautious (high-stakes, data loss) | Serious, transparent, respectful | "Delete account? You'll lose all data and this can't be undone." |
| Successful (completions) | Positive, proportional, brief | "Profile updated. Your changes are live." |

## Terminology — check before naming anything

Maple has documented cases where the **patient-facing term and the internal/code term deliberately differ.** Getting this backwards is the single most common copy error — see `references/terms.md` for the full glossary. The highest-stakes ones to know cold:

- **"Visit"** (patient-facing) vs. `consult`/`consultation` (engineering/data) — current standard, though `terms.md` flags this as an open question rather than a settled convention. Until resolved, default to "visit" for patients; don't assume the split is permanent.
- **"Practitioner"** (patient/partner-facing, always paired with NPs, not MD-only) vs. `Provider` (code term, also the correct word for internal/provider-facing audiences). Don't let "provider" leak into patient-facing copy.
- **"Patient"** (default) vs. `User` — these are distinct data objects (a User can have multiple Patients, e.g. dependents). Don't conflate in specs. Never "customer."
- **"Deactivate"** (patient-facing, for membership cancellation) vs. `Cancellation` (reporting/data field name) — fine internally, keep out of patient copy.
- **"Redirection"** (practitioner declines/redirects a visit) is a distinct concept from **"Care Recommendations"/CR** (provider-facing follow-up feature) — don't conflate in tickets or copy.

If a term isn't in `references/terms.md` yet, add it rather than leaving it undocumented — that file is the living source of truth, not this one.

## Accessibility and usability

Full detail lives in `references/accessibility-guidelines.md` (WCAG-grounded: screen readers, cognitive accessibility, multi-modal cues, forms) and `references/content-usability-checklist.md` (a 0–10 scoring rubric across concise/purposeful/conversational/clear — use it to evaluate or A/B copy options). Load whichever is relevant rather than guessing.

Numbers worth keeping in working memory without opening the reference file:
- **8 words or fewer** = 100% comprehension; **14 words or fewer** = 90%; comprehension drops significantly past 25.
- Reading level: **7th–8th grade** for general/patient-facing copy, up to 10th–11th for technical/professional contexts.
- Line length: 40–60 characters is the readability sweet spot.
- Never rely on color alone — pair with icon + text.

## Quick self-check before shipping copy

- Right term for the concept? (checked `references/terms.md`)
- Right pronoun tier for this surface? (low-tier functional vs. relationship-building)
- Active voice, contractions in, no Oxford comma, Canadian spelling?
- Error/empty/success copy follows its pattern, no dead ends, no blame?
- Comprehension: short sentences, plain words, scannable?
- Would you actually say this out loud?
- **Going into FR too?** Flag it now if the UI has tight space (buttons, fixed-width labels, nav) — French runs 15-20%+ longer than English, and layouts locked to EN character counts will break. This skill doesn't cover FR copy itself; it just catches the handoff before layout gets stuck.

## Reference files

- `references/terms.md` — full patient-facing and internal terminology glossary, including brand↔code mismatches and open questions. Check before naming any Maple concept in copy.
- `references/accessibility-guidelines.md` — full WCAG-grounded guidance: screen reader patterns, cognitive accessibility, forms, translation/localization notes, testing tools.
- `references/content-usability-checklist.md` — scoring rubric for evaluating or comparing copy options.
