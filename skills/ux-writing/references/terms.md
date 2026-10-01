# Maple Terms Glossary (Product & UX Copy)

A living reference for product/UX writers, PMs, and engineers. Consolidates the brand vocabulary rules (Marketing space) with engineering/system naming (Platform Documentation space) so copy decisions and code names stay traceable to one source.

**How to use this doc**
* Check here before naming a new concept in patient- or provider-facing copy.
* If a term isn't listed yet, add it — don't leave it undocumented.
* If "Approved Usage" and "System/Code Equivalent" conflict, flag it in the Notes column rather than silently picking one.
* Source links point to the doc of record; if that doc changes, update this row.

## Patient-facing terms

| Term | Approved Usage | Avoid | System/Code Equivalent | Source | Notes |
|---|---|---|---|---|---|
| Visit | "Visit" for any on-demand or by-appointment session (e.g., "Start your visit now") | "Consultation" when speaking to patients for on-demand care; "consult" as a noun | `consult` / `consultation` (engineering + Looker reporting use "consult" throughout) | Maple vocabulary; Data Glossary & Terminology | Known brand↔code mismatch — copy says "visit," code/data says "consult." Flag explicitly when writing tickets so eng and copy stay aligned. |
| Redirection | "Redirection" — "Our network of practitioners reviewed your request and will redirect you to care that's right for you." | "Rejection" | — | Maple vocabulary | — |
| Practitioner | Default term when speaking to Patients and Partners; always pair doctors with NPs | "GP" or any MD-only term when NPs should be included | `Provider` (engineering/system term — "a user who provides care for patients") | Maple vocabulary; Glossary of Terms & Acronyms | Brand deliberately elevates "practitioner" externally while the codebase still models this as `Provider`. Don't let "provider" leak into patient-facing copy. |
| Provider | Use when speaking to Providers or People (internal); external default is "practitioner" | Referring to providers as "Maple doctors," "Maple dermatologists" (implies ownership) | `Provider` | Maple vocabulary; Glossary of Terms & Acronyms | System/code term and internal-audience copy term are the same word; patient-facing copy term (practitioner) is different. |
| Patient | Default term for who Maple serves; "members" only within the membership package context | "User," "customer" | `Patient` (distinct from `User` — see Data Glossary: a User may have more than one Patient, e.g. dependents) | Maple vocabulary; Data Glossary & Terminology | Copy avoids "user" entirely; engineering uses `User` and `Patient` as two distinct data objects. Don't conflate when writing specs. |
| Prescription | "Prescriptions" for any practitioner-prescribed medication | "Medication," "pills" as a substitute | `Rx` (common internal shorthand) | Maple vocabulary | — |
| Deactivate (membership) | Lead with "deactivate" instead of "cancel" for membership cancellation, patient-facing | "Cancel" (except when a patient explicitly asks to cancel in a support conversation) | `Cancellation` (Looker/reporting field is literally "Cancellation") | Maple vocabulary; Maple Product Glossary | Reporting/data layer uses "Cancellation" as the metric name — that's fine internally, just don't let it surface in patient copy. |
| Specialist | "Specialist" when speaking to patients generally; name the specialty when known (e.g., "dermatologist") | Vague or incorrect specialist labels when specificity is required | — | Maple vocabulary | See Maple vocabulary for full list of medical vs. paramedical specialists. |
| Redirect vs. Care Recommendation | "Redirection" = practitioner declines/redirects a visit request; distinct from "Care Recommendations" (CR), the provider-facing feature for recommending follow-up services | Using "redirection" and "Care Recommendation" interchangeably | `Care Recommendations` / `CR` (Maple feature name) | Maple vocabulary; Glossary of Terms & Acronyms | Easy to conflate in tickets — these are two different product concepts. |

## Maple artifact types

Every consultation can generate up to five clinical "artifacts" — the objects shown in a patient's "Your recent care" feed and in the provider's Actions/Directives panel during a consult. These are concrete product/data objects (not just vocabulary), so it's worth having their definitions in one place before writing copy, specs, or tickets that reference them.

| Artifact | What it is | Code/enum name | Source | Notes |
|---|---|---|---|---|
| Prescription | Provider-issued order for medication, at the provider's discretion (most controlled substances/narcotics excluded); patient accepts and chooses pharmacy pickup or delivery | `prescriptions_feed` / `Prescription` | Prescriptions overview | Distinct from "Bridge prescription" (Beyond ADHD's short-term Rx top-up before a follow-up visit, see below) |
| Medical note | PDF issued at provider discretion, mainly for school/work absence documentation; three subtypes: Practitioner-certified absence note (requires a video visit, capped at 6/12 months), Visit confirmation note (confirms a visit happened, doesn't certify absence), and Custom note (non-absence, e.g. accommodations) | `notes_feed` / `MedicalNote` | Medical notes overview | Also called "sick note" or "doctor's note" informally |
| Lab requisition | Provider order for a physical lab test (bloodwork/urine/stool) or diagnostic imaging (X-ray, ultrasound, CT, etc.); patient downloads, prints, and takes it to a lab of their choice | `requisitions_feed` / `Requisition` | Lab requisition overview | Availability varies by province; cannot be edited once issued — a new one must be created instead |
| Specialist referral | Referral to an in-person, public-system specialist (e.g. dermatologist, psychiatrist, urologist) outside Maple; Maple's Referrals team processes and submits it, the patient doesn't send it themselves | `specialistReferrals_feed` / `SpecialistReferral` | Specialist referral overview | Distinct from Care Recommendation below — a referral sends the patient outside Maple |
| Care recommendation (CR) | Provider-issued recommendation for the patient to book a specific follow-up service *within* Maple (e.g. an OHIP psychiatry follow-up); carries specialty-specific visit limits and expiry | `care_recommendations_feed` / `CareRecommendation` | Care recommendations overview; Glossary of Terms & Acronyms | Not usable outside Maple; already flagged above as distinct from "Redirection" |

*These five are the artifact types currently surfaced in the patient "recent care" feed and the provider consult-room Actions panel. If a new artifact type ships, add a row here.*

## Beyond ADHD program terms

| Term | Approved Usage | Avoid | System/Code Equivalent | Source | Notes |
|---|---|---|---|---|---|
| Beyond ADHD | Always with a space; official title is "The Beyond ADHD program" (lowercase "program" except in titles) | "BeyondADHD," "Beyond" alone | `Beyond` / `BeyondADHD` (internal/engineering shorthand, no space) | Beyond ADHD vocabulary; Glossary of Terms & Acronyms | Internal engineering naming drops the space deliberately — don't "fix" it in code, just keep it out of patient copy. |
| Bridge prescription | Feature name for short-term Rx top-up before follow-up visit | "Bridge dose" | — | Beyond ADHD vocabulary | — |
| Required steps | Pre-appointment homework a patient completes | "Homework," "phase," "stage," "tier" | — | Beyond ADHD vocabulary | Internal/marketing use of "Step 1/2/3" is fine — never patient-facing. |

## Internal/engineering shorthand (reference only — not for patient copy)

| Term | Meaning | Notes |
|---|---|---|
| MNU / MNP / MWU / MWB / MPW | Repo shorthand for native/web patient and provider apps | Glossary of Terms & Acronyms |
| Polaris | 2026 rebranding project name | Glossary of Terms & Acronyms |
| VCNS | Virtual Care Nova Scotia (partner program) | Glossary of Terms & Acronyms |
| PCH | PC Health partnership | Glossary of Terms & Acronyms |

## Unresolved / needs a decision

* [ ] "Visit" (copy) vs. "consult" (code/data) — confirm whether this is a permanent, accepted split or something eng/copy should converge on.
* [ ] Add system-message tone guidance once formalized (see: does product UI skip "we" framing?).
* [ ] Add terms from the EN↔FR glossaries (Maple Product Glossary, UI and Form Title Glossary, Conditions Glossary) as they come up in patient-copy work — not fully cross-referenced here yet.
* [ ] **Date-of-birth field format is unratified — do not invent a rule here.** No brand rule covers date *input* fields (only display copy, e.g. "July 22, 2025"). Known state: the API/database always normalizes to ISO `YYYY-MM-DD` regardless of what's on screen; patient registration's `birthday_at` field currently uses an `MM/dd/yyyy`-style placeholder; a Slack thread (Hulda, Stuart, Sean, Izzy — Nov 2025) flagged that DD/MM/YYYY or YYYY/MM/DD is the safer default for a Canadian audience since MM/DD/YYYY risks misreading a birthdate, and that iOS autofill can paste the device-locale format into a differently-formatted field. Tracked as open bugs **ENG-28733** ("Date field should be in the format DD/MM/YYYY across the platform") and **ENG-28015**, both Backlog. Until one of those ships, don't assume a format when writing or reviewing a DOB field — flag it instead.

---
*Seed sources: Maple vocabulary, Beyond ADHD vocabulary, Glossary of Terms & Acronyms, Data Glossary & Terminology, Maple Product Glossary. Add rows as new terms surface — don't wait for a full audit.*
