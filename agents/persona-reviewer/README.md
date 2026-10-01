# Persona reviewer

Reviews a page, prototype, or flow as one specific person and tells you where that person would understand, trust, hesitate, or leave. It answers "would this person act?", not "is this well designed?"

## When to use it

| Your question | Use |
|---|---|
| Would a skeptical first-time buyer sign up? | persona-reviewer |
| Where would this user stall in the flow? | persona-reviewer |
| Which of these three concepts would this person act on? | persona-reviewer |
| Is the hierarchy, spacing, or copy good? | [`design-crit`](../../skills/design-crit/SKILL.md) |
| Is this ready for handoff? | `design-crit`, then `figma-handoff-check` |
| Both fit and quality, before release | `design-crit` first, then persona-reviewer |

Quick test: if you can describe the reviewer as a person ("a skeptical GP between patients"), use persona-reviewer. If you would describe it as a discipline ("hierarchy and accessibility"), use `design-crit`.

## Set up (once)

1. **Install the agent.** Copy `AGENT.md` to `.claude/agents/persona-reviewer.md` in your project, or to `~/.claude/agents/persona-reviewer.md` to use it everywhere.
2. **Add a persona.** Copy [`templates/PERSONA.template.md`](../../templates/PERSONA.template.md) to `agents/persona-reviewer/personas/<name>.md` and fill it in. See [`examples/example-persona.md`](examples/example-persona.md) for what a filled-in one looks like. Files in `personas/` are git-ignored, so real audience details stay on your machine.
3. **Have a browser available** if you want the agent to use a live page. Without one it works from screenshots and says so.

Do not run it without a persona file. The agent will stop and offer to help you write one rather than invent a person.

## Run a review

Give the agent three things: a persona, an artifact, and optionally the task the persona is attempting.

```text
Use the persona-reviewer agent. Persona: personas/skeptical-buyer.md.
Review https://example.com/pricing. The persona is trying to decide
whether to start a free trial.
```

More examples:

```text
Use persona-reviewer with personas/new-user.md on the screenshots in ./screens/.
Task: create the first invoice.
```

```text
Run persona-reviewer once per persona in personas/ on this prototype and
compare the results.
```

If several concepts exist and you want one reviewed, name it. The agent will ask rather than pick for you.

## What you get back

- A score per dimension and a verdict, in the persona's voice
- A first-person reaction to what is actually on the screen
- An **intent path**: the persona's state at each checkpoint, with the single element that changed it
- **Where I leaned in** and **Where you lost me**
- **Fix first**: one prioritized change
- **What I still need to believe**: the open question blocking a stronger reaction
- **Assumptions**: anything the persona file did not cover
- **Technical notes**: out-of-character findings such as broken links or clipped layouts

## Get better results

- **Be specific.** One person, one goal. "Skeptical buyer deciding on a trial" beats "a user".
- **State the evidence level honestly.** The persona file has an evidence field (researched, composite, assumed). The agent words its claims more cautiously for weaker evidence.
- **Keep the persona's source documents listed.** The agent reads them fresh on every run.
- **Do not brief it on the design.** Rationale makes any reviewer grade what was intended. The agent arrives cold on purpose.
- **Run it twice if the result matters.** The top issue should match. If it does not, the persona is too vague.
- **Use one persona per run.** To compare personas, run it once for each, with a clean context.

## Using it with design-crit

In `design-crit`'s blind panel mode, a persona review runs as an extra reviewer when a persona file exists. Its results show beside the expert scores and are never averaged into them, because they measure fit for one person, not craft. Where the persona disagrees with an expert finding, both views stay visible.

## What it does not do

- It does not edit your design, submit forms, or buy anything. It follows a call to action only far enough to judge the promise.
- It does not replace research with real people. Treat the output as a prompt for what to test, not proof of how users behave.
- It does not judge design quality for its own sake. A polished page that fails the persona is a failure, and an unpolished page that works is not.
- It does not certify accessibility. For that, run a standards-based review.

## Files

- [`AGENT.md`](AGENT.md): the agent definition and its full process
- [`examples/example-persona.md`](examples/example-persona.md): a fictional filled-in persona
- `personas/`: your own personas (git-ignored; see its README)
- [`../../templates/PERSONA.template.md`](../../templates/PERSONA.template.md): the blank template
