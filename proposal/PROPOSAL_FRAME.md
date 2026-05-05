# Proposal frame

A frame for drafting and reviewing proposals. Two modes:

- **Author mode**: copy the template, fill the sections that apply. If you can't fill a required section, that's the gap to close before sending.
- **Reviewer mode**: run the proposal through `## The reviewer pass`. Anything you can't answer from the doc is a comment for the author.

---

## When to use this frame vs. another

This frame is the default for internal technical proposals. Pick a different one when:

- Customer-facing launch or product positioning → `PRFAQ.md` (working backwards from a press release)
- Feature work with elastic scope, fixed time → `SHAPE_UP.md` (appetite-first)
- Leadership memo or board deck where the reader will skim → `PYRAMID.md` (claim-first, MECE arguments)
- Multi-quarter bet or one-way-door decision → `PREMORTEM.md` (failure-first)

## When to skip the frame entirely

For changes under a day of work, fully reversible refactors, or routine tech-debt fixes, write a paragraph in Slack or in the PR description. The frame is overhead for trivial work.

---

## How to read the section tags

Each section in the template is tagged so you know whether to include it:

- **[Always]** - every proposal needs this section
- **[Most]** - skip only with an explicit reason stated in the doc
- **[When applicable]** - include only when the trigger condition (noted in the section) applies

---

## The author template

Copy from here down. Italic prompts get deleted on fill.

### TL;DR  *[Always]*

*Three sentences max. Sentence 1: what you're proposing in concrete terms. Sentence 2: the cost (people, weeks, $). Sentence 3: the one-line ask. The structured fields - decider, owner, deadline, what unblocks on yes - live in `Decision requested`; the urgency case lives in `Why now`. If the reader stops here, they should know what's being asked and what it costs.*

### Audience and decision maker  *[When applicable: SRE, security, legal, finance, or another team can block; or the decider is not your direct manager]*

*Who is this written for, and who decides? Name the approver explicitly. List who is consulted (input expected) vs. informed (no input needed). If the audience is your immediate team and the decider is your manager, skip this section.*

- Decider:
- Consulted:
- Informed:

### Problem  *[Always]*

*What's broken, for whom, with what evidence. Numbers, tickets, customer quotes, incident counts. If the only evidence is "we keep hearing", a measurement milestone (instrument and quantify) precedes any build milestone in `Plan and sequencing` - no exceptions.*

### Why now  *[Most]*

*What changes if we wait one quarter, two quarters. If "now" is not load-bearing, say "this can wait" and propose a later slot.*

### Goal, success metric, and guardrail  *[Always]*

*One north-star metric the business would notice if it moved, plus one guardrail metric that must NOT regress (the "what we'd be embarrassed to game" line). Current value, target, date for each. If current value is unknown, measuring it is M1. Concrete: good = "p95 trial-to-paid time, 14d → 7d, by Q3"; bad = "improve activation".*

| Metric | Role | Today | Target | By when |
| --- | --- | --- | --- | --- |
|  | north-star |  |  |  |
|  | guardrail |  |  |  |

### Options considered  *[Always]*

*2-3 alternatives a thoughtful peer would actually propose, including "do nothing" or "do the cheap version first". For each: one line on the option, and a named cost dimension on which it loses (latency, headcount, blast radius, time-to-ship, vendor risk). "Worse" without a dimension is a strawman.*

- Option A - loses on:
- Option B - loses on:
- Option C (do nothing / minimal version) - loses on:

### Recommended approach  *[Always]*

*The pick. One paragraph on the shape of the work. Separate the conventional parts from the bets - load-bearing assumptions that would invalidate the approach if wrong.*

### Reversibility  *[Always]*

*Yes or no: are any decisions here irreversible (public API shape, data model, tenant identity, customer-visible contract, schema migration, vendor lock-in)? If no, write one line saying so. If yes, list each one-way door, and answer: what does this make harder later (future optionality lost, migrations the next team inherits, adjacent systems constrained)? Reversible calls take minutes; irreversible ones get 10x scrutiny.*

### Out of scope  *[Most]*

*Things that look in-scope but aren't. Naming them up front prevents mid-flight scope creep and tells reviewers what they don't need to debate here.*

- Not doing:
- Not deciding now:

### Plan and sequencing  *[Most]*

*Milestones, each with a description and target date. The first milestone should be the cheapest experiment that proves or kills the approach - if it fails, we stop. Name the kill criteria explicitly.*

- M1 - description (target: date) - kill criteria:
- M2 - description (target: date):
- M3 - description (target: date):

### Cost  *[Always]*

*Two kinds, both required:*

- *Build cost: people (names or roles, FTEs), weeks, $ if relevant.*
- *Ongoing cost after ship: maintenance load, on-call burden, infra spend, vendor renewal, deprecation tax. Who owns it, for how long.*

*Plus opportunity cost: what we won't do because we're doing this. Rough is fine, missing is not.*

### Stakeholders to align  *[When applicable: another team must do work or sign off, or external functions like security, legal, SRE, finance, customer success can block]*

*Who can block this or needs to know before it ships. For each: what they need from us, and when.*

| Stakeholder | What they need | By when |
| --- | --- | --- |
|  |  |  |

### Risks of doing it  *[Always]*

*How this fails. Technical, organizational, customer-facing. For each risk, give it a name and answer two questions: how would we notice, and what's the rollback. "Risks of not doing it" lives in `Why now`, not here.*

**Risk 1: [name]**
- Owner:
- Detect by:
- Mitigation / rollback:

**Risk 2: [name]**
- Owner:
- Detect by:
- Mitigation / rollback:

### Open questions  *[When applicable: you have unresolved questions you want reviewer input on]*

*Questions you don't know the answer to. Each should be answerable, not rhetorical: "should we require SSO for trial accounts" not "is this a good idea". Also note: who pushed back during drafting, and what did you change in response? If nobody pushed back, you didn't show it widely enough.*

- Q1:
- Q2:
- Pushback received and resolved:

### Decision requested  *[Always]*

*The structured ask. The TL;DR carried the one-line version; this is where it gets specific enough to act on. If there is no ask, this is a status update, not a proposal.*

- Decider:
- Owner / DRI (runs the work post-approval):
- Decision needed by:
- On approval:
- If declined or blocked:

---

## The reviewer pass

Run these against any proposal you're reviewing. A "no" or "can't tell" is a comment for the author.

### Blockers (missing answers should send the proposal back)

1. **Buried lede.** Does the first paragraph say what's being proposed and what it costs? If the load-bearing point is in section 4, send it back.
2. **Problem evidence.** Is there a number, ticket, or quote, or is it vibes? Vibes-only must trigger a measurement milestone before any build milestone.
3. **"Why now" is real.** What breaks if this slips a quarter? If the answer is "nothing concrete", the urgency is manufactured.
4. **Metric and guardrail.** If the north-star moves, would the business notice? Is there a guardrail that catches gaming the north-star?
5. **Alternatives are real, not strawmen.** Does each rejected option name a specific cost dimension on which it loses?
6. **Cost is sized - build and ongoing.** Build cost (people, weeks). Ongoing cost (maintenance, on-call, infra) with an owner. Missing either is a blocker.
7. **Decision is specific.** Decider AND DRI named? Does the reader know what to do Monday morning on yes? What's blocked on no?
8. **Kill criteria exist.** Does the first milestone have a defined way to fail? Plans without kill criteria turn into 6-month commitments by default.
9. **Who pays, who benefits.** If the paying team and the benefiting team differ, is the paying team aligned? Is `Stakeholders to align` complete?
10. **Pre-mortem when reversible=no.** If `Reversibility` lists any one-way door, has the most likely 6-month-failure cause been imagined and addressed in `Risks`? If yes is the answer to reversibility and this isn't done, send it back.

### Polish (raises quality but not show-stoppers)

11. **Out of scope is real.** Does the no-gos list prevent actual likely creep, or is it generic?
12. **Open questions are answerable.** Are they specific enough that a reviewer can give a useful answer?
13. **Pushback is shown.** Did anyone push back during drafting, and is the resolution captured?

---

## Anti-patterns to delete on sight

- **Marketing adjectives**: robust, seamless, powerful, cutting-edge, game-changing, next-generation. Cut every one.
- **"Three reasons" when only two are real.** Pad makes the proposal feel weaker, not stronger.
- **Vague baselines**: "some", "manually tracked", "baseline". Lock these down before sending.
- **Recommendation buried at the end.** Lead with the pick, then justify.
- **Risks of not doing it, but no risks of doing it.** Both lists must exist.
- **No cost section.** A proposal without cost is a wishlist.
- **Customer quotes with no source.** Attribute or drop.
- **Unmeasured status-quo claims.** If you make a claim about how the system behaves today, measure it or stop making it.
- **Metric named in TL;DR, never reconnected.** If the headline metric appears once and never traces to the workstreams, the workstreams aren't actually about that metric.
- **Passive voice hiding the owner.** "It will be migrated", "the system will be updated". Name who.
- **Risks listed without owners.** A risk no one owns is a risk no one watches.
- **Dependencies on un-consulted teams.** If team X must do work and they're listed as `Informed`, that's a fiction.

---

## When to invoke deeper review

The frame above is the default pass. For higher-stakes proposals, layer on:

- **Pre-mortem** before committing to a multi-quarter initiative or a one-way door. See `PREMORTEM.md` for a full failure-first frame.
- **Red team** before shipping a non-trivial design or sending to leadership. Adversarial pass on assumptions, dependencies, and failure modes.
- **Council** when the decision involves a real cross-functional tradeoff. Surface disagreement explicitly, name who bears the cost.
- **First principles** when "we've always done it this way" is doing the heavy lifting in the recommendation.
