# Role Guide: Senior Software Engineer (L5 / SDE 2 / SWE 2)

This guide builds on the generic playbook (docs 00–15). The new-grad framing in those docs still applies in spirit — clarify-plan-execute, story craft, agency, the debrief sentence — but at the senior level the bar is materially higher and the rubric is different. Read this guide *after* the generic ones. The deltas matter more than the basics.

It covers the role most companies call **Senior Software Engineer**: roughly L5 at Google/Meta, SDE 2 at Amazon, SWE 2 at most others, IC3 at Microsoft. Typical experience: ~5–8 years post-grad. Below this is "Engineer / SDE 1"; above it is "Staff."

## What the senior bar actually is

A senior is the company's "default productive engineer" — the level at which most ICs settle for their career. The promo and hiring rubric across most companies grades on:

1. **Project ownership.** You can take a feature or system, decompose it, build it, ship it, and operate it. Independently. Without your manager checking in twice a day.
2. **Technical judgment.** You make the right tradeoff calls 8 times out of 10 — and when you don't, you notice and correct. Junior engineers solve problems; seniors solve the right problem.
3. **Influence on a team.** You make other people on your team better — through code review, design review, mentorship of juniors, raising the floor.
4. **Operational maturity.** You think about deployment, monitoring, on-call, incident response, and migration paths *before* shipping. You have scars from things you broke.
5. **Communication with non-eng.** You can talk to a PM, a designer, an exec — and adjust your register.

The bar is *not* "harder LeetCode than juniors." It's broader scope, better judgment, and visible operational instincts. A candidate who solves LeetCode mediums faster than the senior bar but has never shipped to prod will not pass a senior loop.

## The typical loop

Most senior loops are 4–5 rounds + a phone screen. Common shape:

- **Recruiter screen** — 30 minutes. Compensation expectations come up. See doc 09.
- **Hiring manager screen** — career, why-this-company, light technical or system-design probe.
- **Coding round (1–2)** — Live coding. Often medium LeetCode, sometimes adapted to the role's domain.
- **System design round (1–2)** — The single biggest differentiator at senior. More on this below.
- **Behavioral / leadership** — Often called "values," "Bar Raiser" (Amazon), "Leadership and Career" (Meta), or just "BQ." Weighted heavily.
- **Domain or "deep dive"** — Sometimes present. Pick a project from your resume, the interviewer drills as deep as they can on it.
- **Bar raiser / cross-functional** — At Amazon and similar, a calibrated outsider checks the bar.

A 5-round senior loop typically runs 4–5 hours, virtual or onsite. Some companies split across two days.

## Coding at the senior level

Senior coding interviews look superficially the same as new-grad ones. The grading is different.

### What's actually graded

- **Correctness, but assumed.** New grads get partial credit for "almost right." Seniors don't. A senior who fails a medium because of an off-by-one fails the round.
- **Clean code, in real time.** Good naming, sensible decomposition, no clever-but-unreadable hacks. Function-level decomposition, not one giant block.
- **Tradeoffs you call out.** "I'm going with a hash map here for O(1) lookup; the cost is O(n) memory. If we were memory-constrained I'd switch to a sorted array with binary search." Senior signal.
- **Edge cases without prompting.** Empty inputs, single element, overflow, concurrent access if relevant. Don't wait to be asked.
- **Testing instinct.** Walk through your code with a real test case. Mention what unit tests you'd write. State invariants.
- **Recovering when you're wrong.** When the interviewer hints, update visibly and quickly. Defending a wrong solution is worse than being wrong.

### What gets you downleveled

Common patterns that read as "junior":

- Going silent for 3+ minutes.
- Writing code that "almost works" and not testing it.
- Refusing to talk about complexity until asked.
- One-letter variable names.
- A solution that works but is harder to read than necessary.
- Not noticing when a problem is *actually* a known pattern (e.g., not seeing that "find a path between rooms" is BFS).

### What to drill

If you're rusty: 4–6 weeks of NeetCode 150, focused on patterns. Don't grind hard problems unless you're targeting a top-tier company that's known for them.

For top-tier companies (Meta, Google, top trading firms), expect harder mediums and the occasional easy-to-medium hard. Drill:

- Two pointers, sliding window, prefix sums.
- Heaps, priority queues.
- Binary search variants (especially binary-search-on-answer).
- BFS/DFS on grids, trees, graphs.
- Dynamic programming — at least the top 20 patterns (LIS, edit distance, knapsack, intervals, state machines).
- Trees: BST operations, path problems, LCA.
- Topological sort + cycle detection.
- Backtracking — at least canonical templates.

For most companies, the mid-tier hiring loop won't push past medium-level depth. Ask the recruiter what to expect — they'll tell you.

## System design: the senior differentiator

System design is where most senior loops are won or lost. New-grad loops rarely have it; senior loops almost always do, often with two rounds.

### Scope at the senior level

You're designing **a single service or feature**, not the whole company. Typical prompts:

- "Design a URL shortener."
- "Design a rate limiter."
- "Design a notification service."
- "Design a metrics ingestion pipeline."
- "Design the order service for an e-commerce site."

Some senior loops creep into mid-staff territory ("design a chat application that scales"). When in doubt, scope *smaller* and ask the interviewer if they want you to expand.

### The structure

The conventional 4-step framework (clarify, high-level design, deep-dive, scale) still applies. Senior-specific notes:

1. **Clarify (5–8 min)**
   - Functional requirements. What does the system actually do? Which use cases are in scope?
   - Non-functional requirements. Read traffic, write traffic, latency targets, consistency needs, availability target.
   - Constraints — single region or multi-region? Mobile or web or both? Existing infra you have to integrate with?
   - Confirm scope before going further.

2. **Estimate (3–5 min)**
   - Back-of-envelope: QPS, storage, bandwidth.
   - Don't dwell — just get to numbers that ground the rest of the discussion.

3. **High-level design (10–15 min)**
   - Components: clients, API gateway, services, datastores, caches, async workers.
   - Data flow on the main use case.
   - Pick datastores deliberately. SQL vs. NoSQL with reasoning. Don't say "I'll use Cassandra" without saying *why* — and *why not* a simpler option.
   - Identify the 2–3 hard parts of the system. These are what the next phase digs into.

4. **Deep-dive (15–20 min)**
   - Pick the components the interviewer is curious about. Watch their face — they'll lead you to the part they care about.
   - Trade off consistency vs. availability. Single leader vs. quorum. Sync vs. async. Queue vs. log. Batch vs. streaming.
   - Talk schema. Indexes. Hot keys. Sharding. Replication.
   - Failure modes. What happens if the cache fails? If the database is partitioned? If a downstream service is slow?

5. **Operate + extend (5 min)**
   - Monitoring, alerting, dashboards.
   - Deployment + rollback strategy.
   - How would the system evolve if traffic 10xed? What would break first?

### Senior-specific signals

The interviewer is grading whether you can *operate* the system, not just draw it.

- **Pick the simple solution first.** A single-region monolith with a Postgres + Redis often works. If you reach for Kafka and Spark and microservices on a 1K-QPS problem, you fail the judgment check.
- **Talk about operability.** Logging strategy, correlation IDs, runbooks, SLOs. Junior candidates don't think about this; seniors do.
- **Acknowledge what you don't know.** "I haven't worked with [tool] directly — I'd reach for it because [reason], but I'd want to validate its [specific property] before committing." Better than confidently being wrong.
- **Explicitly trade off.** Every choice has a cost. Name it. "I'm picking eventual consistency here. The cost is that read-after-write isn't guaranteed for X seconds. For our use case that's acceptable because…"

### Where to drill

- **"Designing Data-Intensive Applications" (Kleppmann)** — most-recommended book. Chapters on consistency, replication, and partitioning are essential.
- **System Design Primer (GitHub: donnemartin/system-design-primer)** — structured walk through canonical problems.
- **Hello Interview, ByteByteGo, Excalidraw-based mocks** — paid options for guided walkthroughs.
- **3–5 mock interviews** with peers ahead of major loops. The single highest-ROI prep activity.

## Behavioral: the leadership / "BQ" rounds

Senior behavioral interviews are usually graded on a defined rubric — Amazon Leadership Principles, Meta's BQ rubric, etc. (See doc 04's company-specific frameworks section.) Senior-specific deltas:

### Scope expectations

A senior story should show ownership of a non-trivial *project*, not just a task. Interviewers will explicitly probe for scope:

- "How big was the project?"
- "How many people were involved?"
- "What was the timeline?"
- "What was the impact?"

Have hard numbers ready: lines of code, services touched, latency improved, dollars saved, users affected, team members coordinated. If you can't quantify, the impact is too small for the story.

### The "lead without authority" story

Almost every senior loop probes this. "Tell me about a time you drove a technical decision on your team." Or "Tell me about a time you got a peer to change their approach." The rubric:

- Real disagreement (not "we agreed quickly").
- You sought their perspective genuinely.
- You made your case with evidence — design doc, prototype, data.
- You either persuaded them, were persuaded, or found a third path.
- The relationship survived.

Junior candidates fail this by either having no real disagreements or by framing themselves as the obviously-right party. Senior candidates show genuine humility *and* genuine conviction.

### Mentorship signal

You'll likely be asked about mentoring junior engineers. The rubric isn't "how nice were you" — it's "did you make them materially better." Concrete moves to demonstrate:

- Identified a specific gap in a teammate's skill or knowledge.
- Took deliberate action — pairing, code review focus, recommended reading, structured 1:1s.
- The teammate's output measurably changed (code review comments dropped, on-call confidence rose, they shipped X).

Generic "I mentor juniors on the team" is filler. Specific "I noticed Alex's PRs kept getting rejected on testing standards, so I started doing 30-min pairing sessions on test design — within 6 weeks his PR rejection rate dropped from ~40% to ~10%" is signal.

### Failure stories at the senior level

Senior failure stories should be *operational*, not just personal. Examples that read at the right level:

- "I shipped a feature without sufficient load testing; under traffic the database connection pool exhausted and we had a 40-minute outage. Here's what we did to recover, and the change I made to the team's pre-launch checklist that's caught two similar issues since."
- "I made a database schema choice that locked us into a slow migration path. 9 months later we paid for it with a 3-month migration project. The lesson I took to my next design was [specific principle]."

Avoid: "I once underestimated a sprint." That's a junior-level failure.

### Conflict and ambiguity

You will be asked about handling ambiguous requirements, conflicting stakeholders, or unclear priorities. The senior signal: you didn't escalate every decision to your manager. You made calls, communicated them, and reversed them when they were wrong.

## Domain / "deep dive" rounds

Senior loops often include a round where the interviewer picks a project from your resume and drills as deeply as they can. The rule: **own one technical area cold**. If you led a project, know:

- The problem space — why this mattered, what alternatives were considered.
- The architecture — every service, every datastore, every external dependency.
- The hard tradeoffs — and the ones you got wrong in retrospect.
- The operational profile — latency, error rates, on-call load, cost.
- What you'd do differently knowing what you know now.

Bullshitting one of these gets caught. Saying "I led the project but didn't go deep into [area]" is fine — but you should have at least one project you can defend in any direction.

## "Why are you leaving?" / "tell me about your career"

A common opener for senior loops. The trap: complaining about your current employer. Three rules:

1. **No badmouthing.** Even if true. The interviewer doesn't know which side is right and most will side with the absent party.
2. **Lead with what you're moving toward**, not what you're moving away from. "I want to work on systems that operate at higher scale" beats "I'm tired of legacy code."
3. **Be calibrated.** You're not happy enough to stay forever, and you're not desperate enough to take anything. Show that you're choosing carefully.

A senior with a vague "I want growth" answer reads as someone who hasn't thought about what they want next. A senior with a sharp answer ("I've operated on the platform team for three years; my next chapter is closer to product, where decisions trade off business and technical constraints") reads as deliberate.

## Levels and downleveling

The level you target is negotiable but anchored. Downleveling happens when interviewers debrief you as "smart but the scope/judgment is junior-of-senior."

Signals that protect against downleveling:

- Consistent quantified scope ("led a 6-engineer effort," "owned a service with 30K QPS").
- Operational maturity in stories (you talk about ops naturally, not as an afterthought).
- Calibrated technical opinions (you have positions, you can name what would change them).
- Mentorship that visibly worked.

Signals that trigger downleveling:

- Stories framed as "I did X" without context of how it fit into a larger effort.
- No real failure stories with operational consequences.
- Defending wrong technical choices instead of updating.
- Coding round fumbles on basic patterns.

If you're downleveled, you can usually push back once: "Based on the scope of what I've been doing for the past three years and the comp at my current level, the senior leveling fits better. Could you walk me through what specifically pointed to a lower level so I can address it?" Sometimes successful, often not.

## Compensation at the senior level

Senior comp varies wildly. Major US tech, mid-2020s rough bands (verify on Levels.fyi):

- **Big tech (Meta, Google, Amazon equivalents):** $300K–$500K+ total comp.
- **Strong mid-tier (most public companies, late-stage startups):** $250K–$400K total comp.
- **Smaller companies / earlier startups:** lower base + higher equity variance.

Total comp at senior is heavily equity-weighted. RSU refresh grants matter more than the initial grant for long-term comp. See doc 09's equity literacy section.

Negotiation has more room at senior than at new-grad. A 10–25% bump from initial offer to final is common with 1–2 competing offers. Don't accept the first number.

## Pre-loop checklist

72 hours before a senior loop:

- 5–10 medium coding problems, focused on the patterns the company is known for.
- 1–2 mock system design rounds with a peer at your level or above.
- Re-read your top 3 projects; have hard numbers and tradeoffs cold.
- Practice the 5–6 most likely behavioral questions out loud, timed.
- Re-read doc 15 (the debrief doc). Pick the 1–2 sentences you most want each interviewer to write.
- Look up your interviewers on LinkedIn. Note their tenure, prior companies, recent posts.

## What separates the standout senior from the passable

Beyond doc 15's general "shine" guidance:

- **Owns a real opinion on team-level tradeoffs.** "Microservices were the right call here because X; on a previous team I'd have gone the other way because Y."
- **Talks about ops the way a chef talks about prep.** It's not an afterthought. They wake up thinking about pager fatigue, error budgets, cost, latency tails.
- **Has scars and shows them.** A real failure with real cost, named clearly, with a real lesson and a real follow-up application of that lesson.
- **Mentors visibly without pretending to be a manager.** They've raised the bar on their team without trying to manage anyone.
- **Calibrated on their own gaps.** Knows what they don't know — and has a plan or a partner for it. The candidate who says "I haven't operated multi-region; I'd lean on someone who has and learn fast" reads as senior. The one who pretends they have reads as junior.
- **Has an opinion about what their next team should *not* do.** "I'd push back on premature microservices in a 5-engineer team." Real, defensible, useful in week one.
