# Proposal frame

A frame for drafting and reviewing proposals. Two modes:

- **Author mode**: copy the template, fill each section. If you can't fill it, that's the gap to close before sending.
- **Reviewer mode**: run the proposal through the questions in `## The reviewer pass`. Anything you can't answer from the doc is a comment for the author.

The frame works for technical proposals, strategy memos, and quarterly bets. It does not replace an RFC for design specifics, but feeds into one.

---

## The author template

Copy from here down. Each section has a prompt in italics - delete the italics when you fill it in.

### TL;DR

*Three sentences max. Sentence 1: what you're proposing. Sentence 2: why now. Sentence 3: what you need from the reader (approve, headcount, alignment, sign-off). If the reader stops here, they should know what's being asked.*

### Problem

*What's broken, for whom, with what evidence. Numbers, tickets, customer quotes, incident counts. If the only evidence is "we keep hearing", say so and flag it as the first thing to instrument.*

### Why now

*What changes if we wait one quarter, two quarters. If "now" is not load-bearing, say "this can wait" and propose a later slot. Honest timing beats fake urgency.*

### Goal and success metric

*One north-star metric. Current value, target, date. If the current value is unknown, the first milestone is measuring it. Avoid vanity metrics - pick the one that, if it moves, the business notices.*

| Metric | Today | Target | By when |
| --- | --- | --- | --- |
|  |  |  |  |

### Options considered

*2-3 alternatives that a thoughtful peer would propose, including "do nothing" or "do the cheap version first". For each: one line on the option, one line on why it loses. If you can't name a real alternative, you haven't thought hard enough yet.*

- Option A:
- Option B:
- Option C (do nothing / minimal version):

### Recommended approach

*The pick. One paragraph on the shape of the work. Call out which parts are conventional and which are bets.*

### Plan and sequencing

*Milestones with dates. The first milestone should be the cheapest experiment that proves or kills the approach - if it fails, we stop. Name the kill criteria explicitly.*

- M1 (week X): ... - kill criteria: ...
- M2 (week Y): ...
- M3 (week Z): ...

### Cost

*People (names or roles, FTEs), weeks, $ if relevant. Opportunity cost: what we won't do because we're doing this. If you don't know the cost, the proposal isn't ready - rough is fine, missing is not.*

### Risks of doing it

*How this fails. Technical risks, organizational risks, customer-facing risks. For each, one line on how we'd notice and one line on the rollback. "Risks of not doing it" lives in `Why now`, not here.*

- Risk:  | Detect by:  | Mitigation / rollback:

### Reversibility

*Which decisions are one-way doors (public API shape, data model, tenant identity, customer-visible contract, schema migration). Anything reversible can be decided fast. One-way doors get 10x more scrutiny.*

### Decision requested

*What you need from the reader. Be specific: "approve N FTEs for Q3", "sign off on architecture", "align on metric definition", "block on customer comms". If there is no ask, this is a status update, not a proposal.*

---

## The reviewer pass

Run these against any proposal you're reviewing. A "no" or "can't tell" is a comment for the author.

1. **Buried lede.** Does the first paragraph say what's being proposed and what it costs? If the load-bearing point is in section 4, send it back.
2. **Problem evidence.** Is there a number, ticket, or quote? Or is it vibes? Vibes are a fine starting point but should be named as such.
3. **"Why now" is real.** What breaks if this slips a quarter? If the answer is "nothing concrete", the urgency is manufactured.
4. **Metric is load-bearing.** If the metric moves, would the business notice? Or is it a proxy that nobody acts on?
5. **Alternatives are real, not strawmen.** Are the rejected options ones a thoughtful peer would actually propose? Is "do the cheap version first" considered? If alternatives are missing, the recommendation isn't trustworthy yet.
6. **Kill criteria exist.** Does the first milestone have a defined way to fail? Plans without kill criteria turn into 6-month commitments by default.
7. **Cost is sized.** People, weeks, opportunity cost. Rough is fine. Missing is a blocker.
8. **Pre-mortem the recommendation.** Imagine it shipped and failed in 6 months - what's the most likely cause? Is that cause addressed in `Risks`?
9. **Who pays, who benefits.** Same team? Different teams? If different, is the paying team aligned?
10. **One-way doors flagged.** Are the irreversible parts called out separately, or buried?
11. **Decision is specific.** Does the reader know what to do Monday morning if they say yes? If they say no, what's blocked?

---

## Anti-patterns to delete on sight

- **Marketing adjectives**: robust, seamless, powerful, cutting-edge, game-changing, next-generation. Cut every one.
- **"Three reasons" when only two are real.** Pad makes the proposal feel weaker, not stronger.
- **Vague baselines**: "some", "manually tracked", "baseline". Lock these down before sending.
- **Recommendation buried at the end.** Lead with the pick, then justify.
- **Risks of not doing it, but no risks of doing it.** Both lists must exist.
- **No cost section.** The most common failure mode. A proposal without cost is a wishlist.
- **Customer quotes with no source.** Attribute or drop.
- **"Self-healing stays a slide" style claims.** If you're going to make a claim about the status quo, measure it or stop making it.
- **Metric named in TL;DR, never reconnected.** If the headline metric appears once and never traces to the workstreams, the workstreams aren't actually about that metric.

---

## When to invoke deeper review

The frame above is the default pass. For higher-stakes proposals, layer on:

- **Pre-mortem** before committing to a multi-quarter initiative or a one-way door. Imagine failure, walk back the causes, fund the top 1-2 pre-actions.
- **Red team** before shipping a non-trivial design or sending the proposal to leadership. Adversarial pass on assumptions, dependencies, and failure modes.
- **Council** when the decision involves a real cross-functional tradeoff. Surface disagreement explicitly, name who bears the cost.
- **First principles** when "we've always done it this way" is doing the heavy lifting in the recommendation.
