# 06 — Case Studies

Case studies are common in product, consulting, marketing, strategy, analytics, and ops roles. They are also frequently bundled into senior-level technical loops as "guesstimate" or "business sense" rounds. The format varies, but the underlying skill is the same: structured thinking out loud.

## What they're testing

- **Structure.** Can you decompose a vague problem into parts?
- **Quantitative reasoning.** Can you handle numbers without panicking?
- **Business intuition.** Do you understand customers, markets, tradeoffs?
- **Communication.** Can the interviewer follow your thinking and steer it?
- **Judgment.** Can you prioritize, make a recommendation, and defend it?

The right answer almost never matters as much as the path you took to get there.

## The universal frame

Regardless of case type:

1. **Listen and restate.** Repeat the prompt back. "What I'm hearing is… is that the question?"
2. **Clarify the goal.** What does success look like? A decision? A number? A recommendation?
3. **Ask 2–4 clarifying questions.** Scope, time horizon, available data, constraints, who the user/customer is.
4. **Propose a structure.** "I'd like to look at this through three lenses: A, B, C. Does that work?"
5. **Walk through each branch.** Stay aware of time. Don't get lost in one branch.
6. **Synthesize and recommend.** End with a concrete answer + caveats + what you'd want to know to be more confident.

Interviewers will interrupt, redirect, and probe. Treat it as a conversation, not a monologue.

## Case archetypes

### Archetype 1: Market sizing / guesstimate

"How many [X] are sold in [Y] each year?"

The frame: assumptions ⇒ population ⇒ filtering ⇒ usage ⇒ result.

Example shape (US market for tennis balls):

- US population ≈ 330M.
- Roughly 1% play tennis regularly ≈ 3.3M players.
- Assume 50 balls/year per player → 165M balls.
- Plus tournaments, schools, casual buyers — call it 200M balls/year.

State assumptions out loud, round numbers aggressively, and sanity-check the result against something you know. Interviewers care about the structure and the calibration, not 4 decimal places.

### Archetype 2: Profitability / root-cause

"Our profit is down 15% YoY — what's going on?"

Frame: revenue vs. cost.

- Revenue = price × volume (× mix). Each lever can shift.
- Cost = fixed + variable. Variable scales with volume.

Walk down: "Is it revenue or cost? If revenue, is it price or volume? If volume, is it customer count or per-customer? If customer count, is it acquisition or retention?" Drill where the interviewer points, but always say where you're heading next.

### Archetype 3: Market entry / "should we"

"Should our company launch [X] in [Y]?"

Frame: market attractiveness × company fit × execution risk.

- **Market:** size, growth, customer needs, competition.
- **Fit:** brand, capabilities, distribution, existing customer overlap.
- **Risk:** capital required, time to break even, downside.

End with: a clear recommendation (yes/no/conditional), the top 2 reasons, the top risk, and what evidence would change your mind.

### Archetype 4: Product sense

"How would you improve [product feature]?" or "Design [X] for [user]."

Frame: user → goals → pain points → solutions → prioritization → metric.

- **User.** Who exactly? Pick a segment. Don't say "everyone."
- **Goals.** What is the user trying to accomplish?
- **Pain points.** Where does the current experience fail them? Be specific.
- **Solutions.** Brainstorm 3–5. Don't fall in love with the first.
- **Prioritization.** Pick one. Justify on impact × feasibility.
- **Success metric.** How would you measure if it worked?

For new grads, the trap is jumping to a clever feature without grounding in a real user pain. Always start with the user.

### Archetype 5: Analytical / data-led

"Sales for product A dropped 20% last week — investigate."

Frame: define metric ⇒ segment ⇒ identify anomaly ⇒ hypothesize ⇒ validate.

- **Define:** is "sales" units, revenue, or both? Compared to what baseline?
- **Segment:** by region, customer cohort, channel, time of day, product variant.
- **Find the anomaly:** where is the drop concentrated? (Often 80% of the drop is in 1–2 segments.)
- **Hypothesize causes:** internal (price change, stockout, marketing pause), external (competitor, seasonality, news).
- **Validate:** what data would confirm or rule out each hypothesis?

This archetype is increasingly common in data and PM interviews — see the role-specific guide for analyst patterns.

### Archetype 6: Behavioral case ("walk me through how you'd…")

"How would you launch a new student org?" "How would you decide which feature to ship next?"

Treat this like an analytical case but with even more clarification. Often the interviewer cares about your judgment under loose constraints. Ask what the goal is, what resources you have, what the timeline looks like.

## Tactics that translate across all cases

- **Out-loud math.** Show every step. "16 × 250 — that's 16 × 25 × 10, so 400 × 10 = 4000." Calculator-perfect math hidden in your head doesn't earn credit.
- **Round aggressively.** 327M Americans = 330M. Saves time and brainpower.
- **State assumptions explicitly and flag them as assumptions.** "I'm assuming a 70/30 retail/online split — interviewer, want me to use a different number?"
- **Use the whiteboard / shared doc.** Writing forces structure. Even on a phone screen, sketch the framework.
- **Prioritize the top 2 branches.** A perfect deep-dive on one branch beats a shallow walk through five.
- **End with the answer, then the caveats.** "My recommendation is yes, conditional on X and Y. The biggest risk is Z, and to gain confidence I'd want data on W."
- **Time check.** "We're about 15 minutes in, I want to make sure I leave time for the recommendation." Interviewers love this.

## Worked example: a profitability case end-to-end

A realistic transcript. Pace, pauses, and the moment of updating a hypothesis matter as much as the framework.

**Interviewer:** A regional grocery chain — 40 stores in the Midwest — has seen profit margin drop from 4% to 2% over the last 18 months. The CEO wants to know why and what to do. Take it from here.

**Candidate:** Let me restate to make sure I have it: profit margin halved from 4% to 2% over 18 months, 40 stores, regional grocery, Midwest. Goal is to diagnose the cause and recommend an action. A few quick clarifications — is revenue flat, growing, or declining? Has the store count changed? And is this margin drop happening across all stores or concentrated?

**Interviewer:** Revenue is up about 8% over the period. Store count is flat. We don't know yet whether it's concentrated — that's part of what you should figure out.

**Candidate:** Good. Revenue up 8% but margin halved means costs grew faster than revenue — so this is more likely a cost story than a revenue story, but I want to keep both branches open. I'd structure it as: (1) revenue side — price, volume, mix; (2) cost side — COGS, labor, occupancy, shrinkage; (3) segmentation — which stores, which categories. Want me to start on the cost side given the directional clue?

**Interviewer:** Yes.

**Candidate:** Grocery cost stack is roughly: COGS 70–75% of revenue, labor 10–12%, occupancy 3–4%, other 5%. At 4% margin, the math is tight — a 2-point swing means something moved by 2% of revenue, which on a typical $500M chain is $10M a year. Big number, but it can come from a small percentage shift in any large line item. Let me ask: do you know if any of those line items moved noticeably?

**Interviewer:** COGS as a percent of revenue went from 72% to 74%. Labor went from 11% to 12%. Occupancy is flat.

**Candidate:** OK — so COGS is up 2 points and labor is up 1 point. Together that's 3 points of cost increase, and revenue mix only absorbed 1 of it, leaving the 2-point margin drop. COGS is the bigger driver. My initial hypothesis was supplier inflation, but before I commit — is the 2-point COGS increase happening across all categories, or concentrated?

**Interviewer:** Concentrated. Fresh categories — produce, meat, dairy — are running 4 points higher. Center-store packaged goods are roughly flat.

**Candidate:** That changes my read. If it were broad supplier inflation, packaged goods would also be up. Fresh-only points to one of: (a) shrinkage / spoilage rising, (b) a sourcing change in fresh, (c) a pricing decision where they didn't pass through cost increases on fresh to protect customer perception. Can I check shrinkage numbers?

**Interviewer:** Shrinkage in fresh went from 4% to 7% over the same period.

**Candidate:** That's the smoking gun. A 3-point shrinkage increase on fresh — fresh is roughly 35% of grocery revenue — translates to about 1 point of total margin, which is half the gap. The other point is likely the labor increase plus some pass-through pricing softness. So the updated hypothesis: the fresh shrinkage problem is the primary driver, not broad inflation.

Why is shrinkage up? Possibilities: forecasting/ordering broke (overordering perishables), cold chain issue, store-level execution (not rotating stock), or a category expansion that outran operational capacity. I'd want to check whether shrinkage is concentrated in specific stores or specific subcategories.

**Interviewer:** It's concentrated in 12 of the 40 stores, and disproportionately in produce.

**Candidate:** Then this is operational, not strategic. Twelve stores running hot on produce shrinkage suggests a store-management or process issue, not a chain-wide sourcing problem.

**Recommendation:** Short term — deploy a shrinkage task force to those 12 stores: audit ordering patterns, cold-chain compliance, and stock rotation, with weekly shrinkage reporting. Target getting those stores back to chain average within 2 quarters, which recovers ~0.7 points of margin. Medium term — invest in demand-forecasting tooling for produce, which addresses root cause across all stores. Top risk: if shrinkage is symptom of a deeper labor/training issue, the task force won't stick. To gain confidence I'd want to see staff turnover by store and whether the 12 problem stores correlate with recent manager changes.

## Practice protocol

- **Read 1 case per day** for 2–3 weeks before case-heavy interviews. Out loud. Time it.
- **Casebooks** from MBB and top MBA programs are free online. Use them for structure, not for memorization. Real cases will twist the frame.
- **Mock cases with a partner** — minimum 5 before any real case interview, ideally 10+. Switch roles. Giving feedback teaches you the rubric.
- **Review your math.** Most candidates lose points on arithmetic, not framework. Practice mental math drills (10 minutes a day).

## Mistakes that fail cases

- **Dumping a memorized framework** before listening. The interviewer can tell.
- **Getting lost in one branch** for 10 minutes. Watch the clock and pivot.
- **Forgetting to recommend.** A case without a recommendation reads as analysis paralysis.
- **Defending a wrong answer.** If new info contradicts you, update visibly. "Given that, I'd revise my view to…"
- **Being afraid of numbers.** It's a math test wearing a business suit. Practice arithmetic.
- **Long silences.** Same rule as technical interviews — narrate.
