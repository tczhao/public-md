# Role Guide: Data / Business Analyst

This guide builds on the generic playbook (docs 00–15). Read it after, not instead of. Where the generic doc says "tailor for your role" — this is the tailoring.

It covers the umbrella of analyst roles new grads target: **data analyst, business analyst, BI analyst, marketing/product/operations analyst, business intelligence engineer, analytics consultant**. Where roles diverge meaningfully, this doc calls it out.

## What these roles actually do (and how they differ)

- **Data analyst.** Centralized or embedded in a function. Writes SQL daily, builds dashboards, answers ad-hoc questions, runs experiments or describes outcomes. Tools: SQL, Python or R (sometimes), Tableau / Looker / Power BI / Mode, sometimes dbt and version control.
- **Business analyst.** Heavier on stakeholder facilitation and process work. Often translates between business teams and technical teams. Tools: SQL (sometimes), Excel / Power BI heavily, requirements docs, sometimes BPMN diagrams. Can mean very different things at consulting firms vs. enterprise vs. startups.
- **BI analyst / BI engineer.** Closer to the data infrastructure. Owns dashboards, semantic layers, and often dbt models. Tools: SQL, dbt, BI tool of choice, sometimes Airflow. Closer to a junior analytics engineer at modern data teams.
- **Marketing / product / ops analyst.** Function-embedded analyst. Specialization layer on top of data analyst. Tools overlap heavily; domain knowledge of the function matters more.
- **Analytics consultant.** Client-facing. Mix of analyst work + project management + presenting. Tools: Excel and PowerPoint dominate; SQL secondary at most firms.

The common core across all of these:

- **SQL is the lingua franca.** If you can't write a clean window function under pressure, you'll struggle.
- **Communication is the other half of the job.** The best query is worthless if the stakeholder can't act on it.
- **Tradeoff judgment.** Faster vs. more accurate, deeper vs. broader, ad-hoc vs. productized — analysts make these calls daily.

## How the rubric differs from generic engineering interviews

Generic technical interviews grade primarily on algorithmic problem-solving. Analyst interviews grade on:

1. **SQL fluency** — clean, correct, idiomatic queries.
2. **Stats and experimentation reasoning** — at a practical, not academic, level.
3. **Business sense** — defining metrics, framing problems, recommending actions.
4. **Communication** — explaining numbers to non-technical stakeholders without losing precision.
5. **Tool fluency** — Tableau, Excel, dbt, etc., depending on the role.

DSA / coding interviews are rarer and usually lighter when present. The standout candidates are often *not* the strongest pure programmers — they're the ones who blend SQL fluency with business judgment.

## The typical loop

A 4–5 round analyst loop usually contains some mix of:

- **Recruiter screen.** Standard. See doc 04.
- **Hiring manager screen.** Why this role / why this company / walk through resume / 1–2 light analytical questions.
- **SQL technical.** 30–60 minutes. Live or take-home.
- **Analytical case / business case.** "A metric dropped — diagnose it" or "How would you decide whether to ship X?"
- **Stats / experimentation.** Sometimes a separate round, sometimes folded into the case.
- **Behavioral / culture / cross-functional.** Often with a future stakeholder (PM, marketing lead, ops manager).
- **Take-home.** Common: clean a dataset, build a dashboard or analysis, write a recommendation. 4–8 hours of work; often the heaviest signal in the loop.

Smaller companies compress this to 2–3 rounds + take-home. Big tech analyst loops are often 4–6 rounds.

## SQL: what to actually drill

Most analyst SQL interviews test the same handful of patterns. Drill until each is automatic:

### Foundational

- All four joins (inner, left, right, full) and when each is correct.
- GROUP BY with HAVING; the difference between WHERE and HAVING.
- COUNT(*) vs. COUNT(column) vs. COUNT(DISTINCT column).
- NULL behavior across all of the above. (NULL handling is the single biggest source of subtle wrong answers.)

### Window functions (the biggest separator)

- ROW_NUMBER, RANK, DENSE_RANK — the three are not interchangeable.
- LAG, LEAD — for period-over-period and same-row comparisons.
- Running totals (SUM OVER PARTITION BY ... ORDER BY ...).
- First/last-value aggregations.

If you can't write a top-N-per-group query in 90 seconds without thinking, drill more.

### Date / time

- Date arithmetic, date truncation (DATE_TRUNC), extracting parts.
- Day-of-week / week-over-week / month-over-month framing.
- Cohorting by signup month.

### Cohort & retention patterns

- Day-N retention.
- Funnel conversion (rate from step A to step B).
- Sessionization (gaps and islands — common interview pattern).

### Practical fluency

- CTEs (WITH ...) — preferred over deep subqueries for readability.
- UNION vs. UNION ALL.
- COALESCE, NULLIF, CASE WHEN.
- The Cartesian-product accident and how to avoid it.

### Patterns that show up disproportionately

- "Find users who did A but not B." (LEFT JOIN with WHERE NULL, or NOT EXISTS, or anti-join with EXCEPT.)
- "Find the second-highest X." (Window function, not LIMIT 1 OFFSET 1.)
- "What's the % of users who came back N days later?" (Self-join or window.)
- "Find consecutive days a user was active." (Gaps and islands.)
- "Pivot this long table into wide." (CASE WHEN aggregations.)

### Where to drill

- **DataLemur** — interview-flavored, has good explanations for the harder patterns.
- **StrataScratch** — real-company problems, harder to navigate but high-quality.
- **LeetCode SQL section** — easy + medium are 90% of new-grad interview questions.
- **HackerRank SQL** — many companies still use this for screens; worth a familiarity pass.

Daily floor for 4–6 weeks before peak loops: ~30 minutes of SQL drills. After 100–150 problems across the patterns above, you'll have automaticity.

## The SQL interview itself

Live SQL interviews follow a predictable shape:

1. **Read the schema carefully.** Note column names, types, primary keys, what's nullable. Confirm you understand each table.
2. **Restate the problem.** "I want to find X by Y, where X is defined as Z. Right?"
3. **Think out loud about approach** before typing. "I'd CTE the user-level aggregations first, then join to the orders table, then filter…"
4. **Write a query.** Format readably. Use CTEs for clarity.
5. **Walk through it.** Trace it on a small sample case if possible.
6. **Edge cases.** Empty inputs, NULLs, duplicates, ties on rankings, time zones.
7. **State assumptions you made.** ("I assumed signup_date is in UTC. If it's in user-local time, the day-N retention math shifts.")

Common interviewer follow-ups:

- "What if the table had 1B rows? Would your query still work?" — discuss indexes, partitioning, materialization.
- "What if requirements changed to N?" — adapt without rewriting from scratch.
- "How would you sanity-check this in production?" — show you know the difference between "the query ran" and "the answer is right."

## Stats and experimentation: the practical layer

You don't need a stats degree. You need to be able to *talk through* the following at a working level:

- **A/B test design.** Hypothesis, MDE, power, run length, randomization unit, peeking, multiple comparisons.
- **What a p-value actually means** (and what it doesn't). Many candidates fumble this.
- **Confidence intervals** — interpretation, when to use vs. p-values.
- **Sample size and power** — directional intuition: bigger N = smaller MDE you can detect; effect size and variance both matter.
- **Common pitfalls:** novelty effects, weekend/weekday variance, segment heterogeneity, network effects, simpson's paradox.
- **Causation vs. correlation** with at least one real example you can defend.

For role-specific depth:

- **Marketing / growth analyst:** stronger on attribution, MMM-light, channel-level uplift, customer-segment cohorts.
- **Product analyst:** stronger on feature experiments, exposure-vs-treatment definitions, retention metrics, leading vs. lagging metrics.
- **Operations analyst:** stronger on time-series, queueing, capacity, anomaly detection.

A common interview question: *"You ran an A/B test and the lift is significant — would you ship?"* The right answer is never just "yes" or "no." Talk through: was the experiment well-designed? What's the segment-level picture? What's the long-term cost? Are we sure the metric we improved is the metric we care about?

## Analytical / business case: the analyst's bread and butter

Two flavors dominate analyst interviews:

### Flavor 1: "A metric dropped — investigate."

Frame: define → segment → isolate → hypothesize → validate.

1. **Define the metric precisely.** Sales = revenue or units? Compared to what baseline? Over what time window?
2. **Segment.** By region, channel, product, customer cohort, day of week. The drop is almost always concentrated.
3. **Isolate.** "80% of the drop is in segment X" tells you where to look.
4. **Hypothesize causes.** Internal (price change, stockout, marketing pause, bug) and external (competitor, seasonality, news, weather).
5. **Validate.** What data confirms or rules out each hypothesis? What would you query?

The standout candidate names what they'd query for each hypothesis, in plain SQL terms. Not "I'd look at marketing data" — "I'd join the campaign log to the daily sales by channel and check if pause dates align with the drop."

### Flavor 2: "How would you measure / decide / prioritize X?"

Frame: goal → metric → tradeoffs → recommendation.

1. **Clarify the decision being made.** "Are we asking whether to launch, when to launch, or how to measure success?"
2. **Define the metric** that captures success, and one or two guardrails. Be explicit about the tradeoff. ("Optimizing for conversion rate alone risks NPS — I'd want both.")
3. **State assumptions.** Time horizon, population, available data.
4. **Recommendation.** What you'd advise, why, and what would change your mind.

For both flavors, the standout move is *making a recommendation*. Cases die when candidates analyze without committing.

## Take-home assignments: the heaviest signal

Many analyst loops include a take-home. They're the heaviest single signal in the loop because they show how you think when no one's watching. Generic advice in doc 05 applies — and these are the analyst-specific layers:

### Spend 20% of your time on framing

Before any query, write down:

- What is the actual question being asked?
- What's the implicit business decision behind the question?
- Who's the audience for the deliverable, and what do they need?

The strongest take-homes start with framing, not data. The mediocre ones dive in and produce 30 charts that don't answer anything.

### One-pager + appendix

Structure the deliverable as:

- **Page 1:** TL;DR — the answer / recommendation, the 3 most important findings, the 1 caveat.
- **Page 2–3:** The work — methodology, key charts, key numbers.
- **Appendix:** SQL queries, caveats, what you'd do with more time.

Senior people read page 1 and stop. Make sure they can.

### Polish the 3 charts that matter, not all 12

A senior interviewer can spot a candidate who built 12 mediocre charts vs. 3 sharp ones. Pick the 3 that prove your recommendation. Title each chart with a sentence that says what the chart shows ("Mobile conversion fell 30% after the v2 release — desktop unchanged"), not a label ("Conversion by platform").

### Reproducibility matters

If the role has any data engineering proximity (BI engineer, analytics engineer):

- Pin dependencies (`requirements.txt`, `pyproject.toml`, or equivalent).
- Single-command run if possible.
- Sample data included or downloadable.
- README that explains what's where.

For pure analyst roles, you can be lighter on this — but a clean repo still impresses.

### Show one extra thing

One small bonus that wasn't asked for: a sensitivity analysis, a follow-up question you'd want to investigate, a quick second cut at the data. *One* extra, polished. Five extras = bloat.

## Behavioral interviews: analyst flavor

Generic STAR rules apply (doc 04). Analyst-specific signals interviewers probe for:

- **Stakeholder management.** "Tell me about a time a stakeholder disagreed with your analysis." Answer should show: you understood their concern, you stress-tested your work, you either updated or held your ground with evidence.
- **Translating data to action.** "Tell me about a time you presented data and it changed someone's decision." The "changed someone's decision" part is what makes the story land. Without it, the story is just "I ran an analysis."
- **Handling ambiguity.** "Tell me about a time the question was unclear and you had to define it." Analysts get vague asks daily. Show how you scope.
- **Numerical judgment / sanity checking.** "Tell me about a time a number looked wrong and you investigated." Analysts who can't smell-test their own results are dangerous; show you can.
- **Quantitative comfort.** Be ready to do mental math during behavioral rounds — interviewers slip in "what's 12% of 4500?" to gauge ease with numbers.

## "Walk me through your project"

Almost guaranteed in analyst interviews. The structure:

1. **The business question.** What were we trying to figure out? Why did anyone care?
2. **The data.** What did you have? What was missing? What was messy?
3. **Your approach.** How you framed the analysis, what you considered and rejected, what you ended up doing.
4. **The findings.** Quantified.
5. **The recommendation and what happened.** Did anyone actually act on it? If not, why not? If yes, what was the outcome?

Be ready for follow-ups like:

- "What was the hardest part?" — Have a real answer with a real tradeoff.
- "What would you do differently?" — Have a real answer that shows judgment, not false modesty.
- "How did you validate your numbers?" — Have a real answer about sanity checks.
- "What did you do about [specific edge case]?" — Pre-empt by mentioning it before they ask.

## Tools depth

You don't need to be expert at all of these. Pick what's relevant to your target roles:

- **SQL:** non-negotiable. Postgres syntax is the default for interviews; minor variations exist.
- **Python:** pandas + matplotlib at a working level. Numpy basics. Don't lie about ML you haven't done.
- **R:** if your school taught it, fine — many roles accept it. tidyverse + ggplot.
- **Excel:** XLOOKUP / INDEX-MATCH, pivot tables, basic financial modeling. Most entry-level BA roles still live in Excel.
- **Tableau / Looker / Power BI:** know one well. Be able to talk about when you'd pick one over another at a high level.
- **dbt:** increasingly expected for analytics engineering roles. Worth a 20-hour investment if you're targeting those.
- **Git basics:** clone, branch, commit, push, PR. Don't pretend you've done more than you have.

## Resume bullets — strong vs. weak (analyst-flavored)

| Weak | Strong |
|---|---|
| "Worked with SQL to analyze data." | "Wrote SQL queries against a 10M-row Postgres database to track weekly cohort retention; identified a 12% drop in week-2 retention for a specific signup channel that led to a fix shipped by the marketing team." |
| "Built dashboards in Tableau." | "Designed and built a 6-tab Tableau dashboard tracking 14 KPIs across 5 business segments; replaced a manual weekly report saving the analytics team ~6 hours/week and adopted by 30+ business users." |
| "Did data cleaning on a class project." | "Cleaned and joined 4 disparate datasets totaling 200K rows in pandas; resolved 30+ schema mismatches and removed an 8% duplicate rate, enabling downstream model training." |
| "Took a stats class." | "In Bayesian statistics coursework, designed and analyzed an A/B test for a campus food delivery app; team finding (15% conversion lift in the variant) was implemented by the student-run business." |

## What separates the standout from the passable in this role

Going beyond the rubric (and beyond doc 15's general "shine" list), the analyst-specific differentiators:

- **Smell test reflex.** When given a number, the standout candidate's first move is to ask "does that number make sense?" — they sanity-check before they trust. This is the single most-named signal at top firms.
- **Knowing what *not* to do.** Standout candidates push back on bad questions. "Before I run that analysis, I want to flag — the way the metric is defined, this analysis won't tell us what we think it does." Junior candidates execute. Standout junior candidates execute *and* call out scoping issues.
- **Tight, honest writing.** Most analysts write loosely. The standout writes a 4-line Slack update or 1-page memo that gets the point across without reading-between-the-lines. Demonstrate this in your take-home.
- **One genuine technical interest.** Standout candidates have a thing — dbt, causal inference, time-series forecasting, a specific BI tool, a specific dataset they explored. Generic "I love data" reads as nothing. A specific obsession reads as fuel.
- **Visible curiosity about the business.** Top firms hire analysts who get excited about the *domain*, not just the data. "How does retail margin actually work?" "Why does the SaaS metric NRR matter more than ARPU?" Bring real questions; analysts who treat the company as just a backdrop for SQL are easy to dismiss.

## Pre-loop checklist

48 hours before an analyst loop:

- 5–10 SQL drills, including at least 2 window-function problems.
- Re-read the job description; tag the 3–5 keywords most repeated.
- Read the company's blog post or earnings call summary (if public); learn 2 specific facts about their business model.
- Re-read your top 2 projects; have 1 strong reason for every choice you made.
- Re-read doc 15 (the debrief doc). Pick the 1–2 sentences you most want each interviewer to write about you.
- Practice "tell me about a project" out loud once. Time it. Trim it.

## Pre-take-home checklist

Before starting the take-home:

- Read the prompt twice. Note the explicit and implicit asks.
- Pick the 3 questions you'll most prominently answer in the deliverable.
- Sketch the structure of the final report (page 1, page 2, appendix) before any query.
- Set a hard time cap. Add 30 minutes of buffer for polish; don't spend 12 hours on a 4-hour assignment.

## Post-loop: the analyst-flavored follow-up

After your loop, send the standard thank-you (doc 10) plus — if you discussed a specific analytical problem — a short follow-up that *does* something:

> "You asked about how I'd diagnose the engagement drop. Sitting with it more, I realized I missed a useful step: I'd first cohort by signup channel before segmenting by country, since the channel mix likely shifted before the drop. Quick re-frame, but I think it materially changes the order of investigation."

This is the highest-leverage move in the analyst search. It shows the rubric in microcosm: you keep thinking after the interview, you update your view, you communicate clearly. Several offer-leaning hiring managers explicitly remember candidates who did this.
