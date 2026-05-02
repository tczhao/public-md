# Role Guide: Staff Software Engineer (L6 / SDE 3 / Senior+ IC)

This guide builds on the generic playbook (docs 00–15) and on the senior-software-engineer guide. Read the senior guide first if you haven't — most of what's there still applies, just at a higher bar.

It covers the role most companies call **Staff Software Engineer**: roughly L6 at Google/Meta, SDE 3 / Principal SDE at Amazon (terminology varies — some Amazon "Principal" roles are L7-equivalent), IC4 at Microsoft, sometimes "Tech Lead" or "Lead Engineer" at smaller companies. Typical experience: ~9–14 years post-grad, though tenure is a weak proxy. Below this is Senior; above it is Senior Staff / Principal.

The most important framing change from senior: at staff, the job is **technical leadership**, not just technical work. You will be graded on what *other engineers* did because of you.

## What the staff bar actually is

The staff promo and hiring rubric across most companies grades on:

1. **Multi-team or cross-functional scope.** Your work affects engineers and outcomes beyond your immediate team. You drive technical decisions across team boundaries.
2. **Technical strategy, not just execution.** You decide what to build, not just how. You frame the problem before solving it. You write the design doc that 30 engineers read.
3. **Leverage through other engineers.** Your impact is multiplied by the people you mentor, the standards you set, the systems you build that other teams use.
4. **Influence without authority.** You ship things by getting other people to build them — without being their manager. This is the central staff skill.
5. **Judgment on what NOT to do.** You kill projects, redirect resources, push back on stakeholder asks that aren't worth the cost. Saying no with grace is a staff-level skill.
6. **Long-horizon thinking.** You think 12–24 months out — what will this system look like? What will the team look like? What's the migration path?

The staff bar is not "harder system design." It's *organizational technical leadership*. A candidate who is a 10x coder but has never made another team better will not pass a staff loop at most companies.

## Staff archetypes (Will Larson's framework, useful for self-positioning)

Will Larson's *Staff Engineer* identifies four archetypes that staff engineers tend to inhabit. Knowing your archetype helps you tell the right stories and target the right roles:

- **Tech Lead.** Embedded in a team, drives the technical direction of that team's work. Closest to the senior-staff transition path. Common at most companies.
- **Architect.** Owns the technical direction of a domain or product area, often spanning multiple teams. Less hands-on coding; more design docs and reviews. Common at larger orgs.
- **Solver.** Parachutes into hard problems across the org. The org's "go-to firefighter." Usually emerges in mature companies with complex systems.
- **Right Hand.** Functions as a senior partner to a director or VP, executing and translating their technical agenda. Often emerges from long tenure.

Most staff candidates lean toward one or two archetypes. Loops at different companies emphasize different ones — a startup hiring its first staff is usually looking for a Tech Lead; a big-co hiring for a platform team may be looking for an Architect.

## The typical loop

Staff loops are usually 5–7 rounds + a phone screen, often split across two days. Common shape:

- **Recruiter screen.**
- **Hiring manager screen** — career, scope, why-this-company, light technical probe.
- **Coding round (1, sometimes 2)** — Often de-emphasized at staff. Not the differentiator.
- **System design round (2)** — One product/feature design, one platform-or-architectural design.
- **Behavioral / leadership rounds (1–2)** — Significantly weighted at staff. Often with a director or skip-level.
- **Domain / deep dive** — A project from your resume, drilled deep.
- **Cross-functional / partner round** — With a PM, designer, or skip-level engineer. Tests whether you can operate with non-engineers.
- **Bar raiser / executive round** — Calibrated outsider or senior leader.

A 6–7 round staff loop typically runs 6–8 hours. Some companies front-load technical and back-load leadership; others mix.

## Coding at staff

Coding rounds at staff are usually present but de-prioritized. The interviewer is checking that you haven't lost touch — not whether you're faster than the senior bar.

What changes vs. senior:

- **Less weight in the final decision.** A botched coding round at staff is recoverable if other rounds are strong; at senior it's often disqualifying.
- **More questions about engineering practice.** "How would you write tests for this?" "What would the code review for this look like?" "How does this interact with the rest of the codebase?"
- **More tradeoff conversation, less typing.** A staff candidate who spends 15 minutes on a problem and 15 minutes discussing tradeoffs is well-calibrated.
- **The "I would normally pull in a library here" move.** Staff engineers don't write quicksort from scratch in a real codebase. Naming the right library and explaining when you'd build vs. buy is signal.

If you've been senior for 3+ years and feel rusty on coding, allocate a few weeks of NeetCode 150 to refresh the patterns. You don't need to grind hard problems unless you're targeting a top-tier company that's known for them.

## System design: at staff

Staff system design is the centerpiece. At senior you're designing a service; at staff you're designing **a platform, a multi-team architecture, or an organizational technical strategy**.

### Two flavors of staff system design

**Flavor 1: Multi-service / scaling.** "Design a real-time recommendation system at scale." "Design the metrics platform for a 5,000-engineer company." "Design how we'd migrate from a monolith to a service-oriented architecture across 30 teams."

The shape is similar to senior, but:
- More services, more interactions.
- Failure modes across system boundaries become central.
- Migration paths matter — you can't say "we'd build this from scratch" when there's a real existing system.
- Organizational tradeoffs surface: who owns what, how are interfaces versioned, what's the deprecation policy.

**Flavor 2: Architectural / strategic.** "We have three competing internal frameworks for X. How do you pick a winner and migrate?" "Engineers across teams keep reinventing Y. What do you do?" "How do you decide between buying and building Z?"

These prompts test technical judgment more than technical depth. The shape:
- Frame the problem precisely. What are we actually solving? What's success?
- Identify constraints — political, technical, timeline, team-skill.
- Generate 3–4 options. Trade them off explicitly.
- Pick one. Own it. Name what would change your mind.
- Plan execution — phases, owners, communication, risk mitigation.

### Staff-specific signals in design

- **Scoping the problem.** Most candidates jump in. Staff candidates spend 5–10 minutes scoping. "Before I design anything: who's the user, what's the target throughput, what's existing, what's the integration surface, what's our timeline horizon?"
- **Designing for the org, not just the system.** "I'd put this team-owned interface here so [team A] doesn't block [team B] every time we change the schema." Organizational design baked into technical design.
- **Migration paths.** A senior candidate designs the end state. A staff candidate designs the migration. "We'd run dual-writes for 4 weeks, then switch reads behind a flag, then deprecate the old path. The risk is X; we'd mitigate with Y."
- **Operability at scale.** Not just monitoring this service — how does on-call rotate, who owns escalations, how do we onboard a new team to this platform.
- **Calling out cost.** Both engineering cost (how many quarters of work) and runtime cost (compute, storage, support burden). Staff candidates do this naturally.
- **Pushing back on bad scope.** "I'd actually argue against doing this at all if [condition]. Here's the cheaper path that gets us 80% of the value."

### What gets graded down at staff

- Designing the cool system instead of the right one.
- Skipping migration concerns.
- Not engaging with organizational reality. ("In my design, team X just hands ownership to team Y" with no thought to whether X would agree.)
- Reaching for trendy tech without justification.
- Failing to call out tradeoffs explicitly.
- Forgetting to propose monitoring and operability concerns.

### Where to drill

- **"Designing Data-Intensive Applications" (Kleppmann).** Re-read if it's been a while. The chapters on batch and stream processing, derived data, and the future of data systems matter more at staff.
- **Internal architecture reviews and design docs from your current company.** Better practice than any external resource. Read 10–20 design docs from senior+ engineers; note structure and what they emphasize.
- **Mocks with a staff or principal engineer.** Worth paying for if you don't have one in your network.
- **"Software Engineering at Google" (Winters et al.)** for the org/process side of large-scale systems.

## Behavioral / leadership rounds at staff

This is where most staff loops are won or lost. Companies weight leadership heavily because the gap between senior and staff is leadership, not technical depth.

### The story bank shifts

Your senior story bank covered ownership, mentorship, ambiguity, conflict. At staff, expect probes for:

- **Driving cross-team initiatives.** Tell me about a time you moved something forward across team boundaries.
- **Influencing without authority.** Tell me about a time you got a team that wasn't yours to change direction.
- **Killing or redirecting work.** Tell me about a time you said "we shouldn't do this" — and what happened.
- **Setting technical standards or strategy.** Tell me about a time you defined how something should be done at scale.
- **Mentoring senior engineers.** Tell me about a time you raised the bar on a peer at your level or above.
- **Conflict with leadership.** Tell me about a time you disagreed with a manager / director / VP on technical direction.
- **Operating under organizational ambiguity.** Tell me about a time the right move wasn't clear and you had to commit anyway.

### The "scope" probe

Staff interviewers are calibrating *scope*. They will explicitly probe the size of your impact:

- "How many engineers were affected by this decision?"
- "How long was the project?"
- "What was the dollar impact / latency improvement / cost reduction?"
- "How did this fit into the broader org's priorities?"

Have hard numbers ready. Vague impact = senior story. Concrete cross-team impact with quantified outcome = staff story.

### Influence stories (the central skill)

The single most-asked staff behavioral pattern: "Tell me about a time you got someone you didn't manage to do what you needed."

The rubric:

1. **Real friction.** They had different priorities, beliefs, or constraints. Not "we agreed quickly."
2. **Genuine engagement with their perspective.** You understood why they didn't want to do it. You can articulate their view.
3. **Building shared evidence.** A design doc, a prototype, data, a small POC — something that moved the conversation past opinion.
4. **Compromise where appropriate.** Often the staff move is "I gave up on getting them to build the thing my way; I built a smaller thing they could plug into." Compromise reads as senior maturity.
5. **Sustained relationship.** They're still talking to you after.

Junior version: "I convinced them I was right." Staff version: "We disagreed, I learned what their constraints were, we built a third option that worked for both teams, and now they ping me first when they're considering similar changes."

### Killing-or-redirecting stories

A staff-specific pattern: a story where the right move was to *not* do something. Or to redirect significant work.

Strong shape:

- A real opportunity cost. The team was about to spend significant time on X.
- Your judgment said X wasn't worth it.
- You built consensus (with the team, with the PM, with leadership) to redirect.
- The redirected work paid off — or, more honestly, the killed work would have hurt.

Saying "no" well is a staff signal. Senior candidates execute. Staff candidates execute *and* prevent bad execution.

### "Why staff?" / "what's your scope?"

A common opener. The trap: rambling about your career. Tighten this to 90 seconds:

> "I've been operating at the staff level for the past [N] months — leading the [project/area], driving technical strategy across [scope], mentoring [N] senior engineers. I'm looking to formalize that scope at a place where [specific reason about the company]. What pulled me toward this role specifically is [specific reason about the role]."

## Domain / deep-dive rounds at staff

Senior loops drill into a project. Staff loops drill into a *technical area you claim to own*.

The interviewer's question shape:

- "Walk me through the most complex system you designed."
- "Tell me about a technical area you're an expert in."
- "Pick a technical decision you made that you're most proud of, and walk me through it."

The bar is mastery, not familiarity. You should be able to answer:

- The problem space comprehensively. Why did this matter? Who else has solved variants? How are they different?
- The full architecture, every component, every external dependency.
- Every meaningful tradeoff you made and why.
- The decisions you got wrong and what you'd do differently.
- The operational profile and what you learned operating it.
- Where the system is in 2 years if it's successful.

A staff deep-dive can take 45 minutes with a strong interviewer. They will push until they find your edge. Find your edge in advance — know where your knowledge runs out and have an honest answer for what's beyond it.

## Cross-functional rounds

Many staff loops include a round with a PM, designer, or non-engineering stakeholder. The signal: can you operate with non-engineers without (a) condescending to them or (b) caving on every technical decision?

What lands:

- **Translating technical detail into business framing.** "The reason this is hard is that we'd be locking ourselves into a 6-month migration if user growth doesn't materialize."
- **Asking *their* questions back.** "What's the customer pain point that's driving this? Have we validated it directly with users?" Shows you think past the technical scope.
- **Disagreeing with grace.** "I hear the priority, and here's what concerns me about the timeline. Can we discuss the tradeoff?"

What fails:

- Refusing to engage with business framing. ("That's a product question.")
- Caving immediately. ("Sure, we can ship it in two weeks.")
- Showing visible frustration that they don't understand the tech.

## Compensation at staff

Staff comp varies wildly. Major US tech, mid-2020s rough bands (verify on Levels.fyi):

- **Big tech (Meta, Google, Amazon equivalents):** $500K–$800K+ total comp.
- **Strong mid-tier (most public companies, late-stage startups):** $400K–$650K total comp.
- **Smaller companies / earlier startups:** lower base + significantly higher equity variance and risk.

A few staff-specific comp dynamics:

- **Equity refresh grants matter enormously.** Year 5 cliff is real. Check the company's refresh policy explicitly.
- **Sign-on can be substantial** — especially if you're walking away from unvested equity at your current company. "Make me whole on the unvested" is a routine staff ask.
- **Negotiation has real range at staff.** 15–30% bumps from initial offer to final are common with competing offers. Sometimes more.
- **Title and level negotiation.** At some companies you can negotiate level (staff vs. senior staff). At others the level is rubric-locked. Ask early.

## Pre-loop checklist

72 hours before a staff loop:

- 1–2 mock system design rounds with a staff+ engineer.
- Refresh your top 2 deep-dive projects. Have hard numbers, tradeoffs, and "what I'd do differently" cold.
- Practice 8–10 of the most likely behavioral questions out loud, with the scope-probe follow-ups.
- Review the company's engineering blog, recent architecture posts, and any podcast appearances by the hiring manager or potential interviewers.
- Re-read doc 15 (the debrief doc). Your target debrief sentence at staff is something like: *"Operates at staff scope today. Influence stories were specific and credible. Has opinions, defends them, updates them. Would raise the bar on the team."*
- Look up your interviewers. Note their tenure, prior companies, recent work. Plan one personalized question for each.

## What separates the standout staff from the passable

Beyond doc 15's general "shine" guidance and the senior-specific list:

- **Visibly reasons about the org as a system.** The staff candidate doesn't just say "the team should adopt X" — they reason about who proposes it, how it's reviewed, who owns it long-term, what the migration path looks like, and what the political and technical risks are. They show, in real time, that they think organizationally.
- **Has a real opinion about staff-level tradeoffs.** "I think most companies over-invest in microservices too early." "Internal platforms are usually built by people who didn't have to use them." "Most engineering process exists because of one bad incident that's no longer relevant." Calibrated, defensible, useful in week one.
- **Talks about *not building* with the same energy as building.** A staff candidate who can describe a project they killed, redirected, or scoped down — and the reasoning — is rare and valuable.
- **Treats the interviewer as a peer, not a judge.** Disagrees gently. Pushes back on weak prompts. Brings counter-questions. The goal is a conversation between two technical leaders, not a quiz.
- **Names their current limits.** "I've operated cross-team but not cross-org. The gap I'm closing is [specific thing] and the way I'd approach a cross-org effort on day one would be [specific plan]." Calibrated honesty reads at staff.
- **Has a small, sharp follow-up after the loop.** A 4–6 paragraph note extending the design conversation, the technical strategy discussion, or the leadership probe. Not a thank-you — a continuation. The candidates who win competing staff offers almost always do this.
