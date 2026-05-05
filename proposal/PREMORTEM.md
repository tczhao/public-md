# Pre-mortem-first proposal frame

A frame that inverts the usual proposal structure. Instead of justifying why a plan will work and tacking risks on at the end, write the obituary first. Generate failure causes before the plan exists, walk back the causal chain, then build the proposal around the top pre-actions so mitigations are workstreams, not appendix items.

The technique is Gary Klein's pre-mortem, applied to the proposal itself. The proposal carries its failure analysis with it, so reviewers can see what was considered and what's baked in.

---

## When to use this frame

Best fit: multi-quarter initiatives, one-way-door decisions (data model, public API, tenant identity, customer-visible contracts), projects where the team is already excited (excitement masks risk), and high-cost-of-failure work where the recovery is measured in quarters rather than weeks. If a failure would force a rewrite, a public apology, a migration, or a re-org, this frame earns its overhead.

Bad fit: small reversible changes, well-trodden paths the team has shipped variants of before, and tactical work with tight deadlines where the pre-mortem is overhead the timeline can't absorb. For those, use the default proposal frame and treat pre-mortem as one reviewer question among many.

---

## The author template

Copy from here down. The pre-mortem comes first, on purpose. Each subsection has an italic prompt - delete it when you fill it in.

### Imagined failure scenario

*3-5 sentences, past tense. Open with "It's [date one year out]. The project failed." Describe what happened from the perspective of someone writing the postmortem. Be concrete about what shipped, what didn't, who was unhappy, and what the team is doing now instead. Past tense and specifics force commitment. Hedged language ("if things go wrong", "could potentially fail") signals you're still defending the plan rather than imagining its death.*

### Brainstormed causes

*List at least 7 specific causes. The number is deliberate. The first 3 are the obvious ones - the ones the team has already discussed. The interesting causes (the ones that actually take the project down) tend to surface between cause 4 and cause 7, when the obvious answers are exhausted and you're forced to look at adjacent systems, organizational dynamics, and second-order effects.*

*Each cause should be specific to this project, not a generic risk. "Scope creep" and "key person leaves" apply to every project ever proposed and tell the reader nothing. Replace them with the project-specific version: which scope, creeping in which direction, because of which pressure; which person, owning which knowledge, with what bus factor.*

1.
2.
3.
4.
5.
6.
7.
(more if they're real)

### Clusters

*Group the causes into 3-4 named themes. Naming forces you to see the shape of the failure space. If 5 of your 7 causes cluster into one theme, that's the load-bearing risk and the proposal should be organized around it. If every cause is its own theme, you haven't generated enough causes yet.*

- Theme 1 - [name]: causes [...]
- Theme 2 - [name]: causes [...]
- Theme 3 - [name]: causes [...]

### Causal walk-back for the top 2 themes

*For each of the top 2 themes, walk back 3 links from the imagined failure to today's actions. The format is "X happened because Y, which happened because Z, which happened because today we [concrete action or non-action]." The third link must land on something a person is doing or not doing right now. If it lands on a vague condition ("the team was under-resourced"), keep walking - why under-resourced, decided by whom, in which planning cycle.*

*A real 3-link walk-back changes what you'd put in the plan. If yours doesn't, it's likely 1 link repeated three times in different words.*

**Theme 1 - [name]:**
- Link 1 (failure): [...]
- Link 2 (because): [...]
- Link 3 (today's action): [...]

**Theme 2 - [name]:**
- Link 1 (failure): [...]
- Link 2 (because): [...]
- Link 3 (today's action): [...]

### Top pre-actions

*The 1-2 actions that come directly from the walk-back. Each pre-action gets a concrete owner, a date, and a definition of done. "Hire one SRE in Q2 to own the migration runbook" is a pre-action. "Monitor closely" is not. "Communicate proactively" is not. If a pre-action can't be funded or scheduled, it's an aspiration, not a commitment.*

- Pre-action 1: [what] | owner: [who] | by: [when] | done when: [observable condition]
- Pre-action 2: [what] | owner: [who] | by: [when] | done when: [observable condition]

---

### TL;DR

*Three sentences. What you're proposing, why now, what you need from the reader. If the pre-actions above are load-bearing, name them here - don't bury them in the plan.*

### Problem

*What's broken, for whom, with what evidence. Same standard as the default frame: numbers, tickets, quotes. Vibes are flagged as vibes.*

### Plan with pre-actions integrated

*Milestones with dates. The pre-actions from the pre-mortem are first-class workstreams, not appendix items. If pre-action 1 is "hire one SRE", that hire is M1 or M2, not "ongoing". The first delivery milestone should still have explicit kill criteria.*

- M1 (week X) - includes pre-action [N]: [...] - kill criteria: [...]
- M2 (week Y) - includes pre-action [N]: [...]
- M3 (week Z): [...]

### Cost

*People, weeks, dollars. Include the cost of the pre-actions explicitly. If the pre-actions add 30% to the budget, that's the real cost of doing this safely - don't hide it.*

### Decision requested

*What you need from the reader. Be specific: approve N FTEs, sign off on the pre-actions as funded workstreams, align on kill criteria. If the ask doesn't reference the pre-actions, the pre-mortem isn't connected to the decision.*

---

## Reviewer pass

Specific to pre-mortem-first proposals. A "no" or "can't tell" is a comment for the author.

1. **7+ specific causes.** Did the author generate at least 7, or stop at 3? Count them. The interesting causes live past the obvious ones.
2. **Causes are project-specific.** Are the causes about this project, or generic risks (scope creep, attrition, dependencies slip) that could apply to any project? Generic causes mean the pre-mortem hasn't done its work.
3. **Causal walk-back has real depth.** Does each top-theme walk-back have 3 distinct links, or is it 1 link rephrased three times? Test: does link 3 name a concrete action or non-action happening today, by a named person or team?
4. **Pre-actions are concrete and funded.** "Hire one SRE in Q2" passes. "Monitor closely", "communicate proactively", "stay aligned" fail. Each pre-action needs an owner, a date, and a definition of done.
5. **Pre-actions are first-class workstreams.** Are the pre-actions in the milestone plan with budget and owners, or are they in an appendix titled "risk mitigations" that nobody will fund?
6. **The proposal changed shape because of the pre-mortem.** This is the load-bearing reviewer question. If the plan would look identical without the pre-mortem, the pre-mortem was retrofitted to decorate a pre-existing plan. Ask the author which specific plan element changed because of which specific cause.
7. **Failure scenario is past tense and concrete.** "It's [date]. The project failed because we shipped X without Y" passes. "If things go wrong, the project could fail" fails - hedged language means the author is still defending the plan.
8. **Clusters tell a story.** Do the 3-4 themes name the actual shape of the failure space, or are they just bins? If every cause is its own cluster, more causes are needed.
9. **Cost reflects the pre-actions.** If the pre-actions are real, they cost real money and people. Is that cost in the budget, or hidden?

---

## Anti-patterns specific to this frame

- **Generic risks dressed up as causes.** "Scope creep", "attrition", "dependencies slip", "priorities shift". These apply to every project. If the cause list reads like a risk register from any proposal, it isn't a pre-mortem yet. Push for the project-specific version.
- **Walk-back that stops at the first surface cause.** "It failed because the migration was hard" is link 1. The pre-mortem needs link 2 (why was it harder than expected) and link 3 (what are we doing today that makes link 2 likely).
- **3-link walk-back that's actually 1 link repeated.** "Failed because under-resourced. Under-resourced because team was small. Team was small because we didn't have enough people." Same claim three times. A real walk-back crosses domains - technical to organizational to planning to today's action.
- **Pre-actions phrased as verbs without commitments.** "Monitor closely", "communicate proactively", "stay aligned", "track progress". These are not pre-actions. Replace with concrete commitments: who, what, by when, observable when done.
- **Pre-mortem written after the proposal.** Heuristic for spotting this: if the pre-mortem causes don't change the plan at all, the plan came first and the pre-mortem was retrofitted. Ask "which milestone changed because of which cause" - if the author can't answer, the pre-mortem is decoration.
- **Failure scenario in passive voice or hedged.** "If things were to go wrong, issues could arise." Past tense and active voice are the rule: "We shipped X. Customers Y. The team is now doing Z instead."
- **Pre-actions in an appendix instead of the plan.** If the pre-actions live in a "risk mitigations" section after the milestones, they will not be funded. They have to be milestones, with owners and dates, or they're aspirations.
- **Clusters named after the causes instead of the failure mode.** "Cluster 1: causes 1, 2, 3" is a bin. "Cluster 1: migration runbook gaps" names a failure mode and tells the plan what to do.

---

## When this frame feeds into others

- After the pre-mortem, run a **red team** pass on the resulting plan - the pre-mortem covers failure-by-omission, the red team covers failure-by-attack.
- For cross-functional cost ("the SRE comes from which team's headcount"), pair with **council** so the paying team is in the room.
- If the pre-mortem reveals the framing is wrong (the project shouldn't exist in this shape at all), drop to **first principles** before continuing.
