# Sample report (sanitized)

This is a condensed version of the first real test run, on one section of a production patient-facing web file. Product names, file links and node IDs have been removed.

## Header

- Scope: one section, 11 screens, 669 layers scanned
- Platform: patient web, desktop only for now
- Color tokens: a library "colour mode" collection, treated as semantic
- Spacing source of truth: design system library v1.1
- Previous report: none (baseline)

## Verdict: Not ready

Two blockers: 16 detached library components, and four screens sharing the name "No appointment" when three of them show appointments. Colors and screen text were clean.

## Counts

| Severity | Findings | Layers |
| --- | --- | --- |
| Blocker | 2 | 20 |
| Fix before handoff | 3 | 24, plus 1 decision |
| Nice to have or system gap | 3 | 88 spacing values, 21 generic names, 1 hidden layer |

## Findings

**Blocker: 16 detached components.** 14 copies of a specialty card across 7 screens and 2 copies of a sidebar. Names still matched the library components, so each could be swapped back.

**Blocker: four screens named "No appointment".** Only one showed an empty state. One showed a list of appointments, and two showed a single appointment card and were nearly identical. Suggested names: `Dashboard / No appointment`, `Dashboard / One upcoming appointment`, `Dashboard / Multiple upcoming appointments`, plus a question about whether the near-duplicate was a version or a leftover.

**Fix before handoff: 17 default layer names.** For example `Frame 1948758686` containing a segmented control became `NotesFilter`, and `Frame 1573` containing list items became `NotesList`. Six of them sat inside a detached sidebar and would be fixed by relinking it.

**Fix before handoff: three naming patterns across screens.** `Flow / Screen`, `Screen - State` and `Screen, State` were mixed. Suggested one pattern: `Platform / Flow / Screen / State`.

**Fix before handoff: one local component.** An appointment card lived in the file rather than the library, used 15 times. Flagged as a decision: move it into the design system or tell developers it's new.

**Nice to have, design system gap: 88 unbound padding and gap values.** The source-of-truth library only had five spacing tokens, all card-specific. The values sat on a clean 4px scale (4, 8, 12, 16, 32), which is useful evidence for adding a general spacing scale.

## Change summary for developers

- Dashboard states: no appointment, one upcoming, multiple upcoming, related services only, and dashboard with an upcoming appointment.
- A new general dashboard and a notes history screen with all, not viewed and empty states.
- A new appointment card, local to the file for now, with not started, in progress and completed states.
- Developer decisions: whether the appointment card joins the design system, and which near-duplicate screen is current.
