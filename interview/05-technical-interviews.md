# 05 — Technical Interviews

This document covers the *generic* shape of any technical interview — engineering, data, ML, analytics, quantitative. Role-specific drills live in the role guides.

## What's actually being graded

Every technical interviewer is scoring some combination of:

1. **Problem-solving process** — how you decompose, how you handle stuckness.
2. **Technical fluency** — can you write/use the tool (code, SQL, model) without fighting it.
3. **Communication** — can the interviewer follow your thinking in real time.
4. **Calibration** — do you know what you don't know, do you ask the right questions.
5. **Result quality** — does it work, is it correct, is it efficient enough.

A perfect solution delivered in silence loses to a near-perfect solution explained well. Communication is not bonus — it's a primary axis.

## The universal frame: clarify → plan → execute → verify

Every technical question, regardless of domain, follows this:

### 1. Clarify (2–4 minutes)

Restate the problem in your own words. Then ask:

- **Inputs / outputs / constraints.** Sizes, types, edge cases (empty, null, very large).
- **Examples.** Walk through one example end-to-end before coding. Confirm with the interviewer.
- **Assumptions.** What can you take as given? What needs to be verified?
- **Definition of done.** What's the bar — works on examples, or also handles all edge cases, or also optimized?

Skipping this step and diving in is the #1 reason candidates fail technical interviews on questions they could solve. Slow down.

### 2. Plan (3–5 minutes)

Before writing anything, talk through the approach.

- Sketch the data structures and the high-level algorithm.
- Estimate complexity (time and space).
- Mention 1–2 alternatives and why you're picking this one.
- Get a "yes, sounds reasonable" from the interviewer before coding.

If they object or hint, *listen*. They've done this 100 times — their nudge is information.

### 3. Execute (10–25 minutes)

While you code or query:

- **Narrate.** "I'm going to start by initializing the result set, then iterate over… for each row I'm checking…"
- **Write the skeleton first**, fill in details. Don't write the perfect line out of order.
- **If you get stuck, say so.** "I'm thinking about how to handle the edge case where… let me think for 30 seconds." Silence is worse than admitting you're thinking.
- **Don't fix syntax in your head.** Write something close, run it (if you have execution), and iterate.

### 4. Verify (3–5 minutes)

Before saying "done":

- Walk through your example by hand. Don't trust your code.
- Try at least 2 edge cases out loud: empty input, single element, max size, negatives, duplicates, nulls.
- State complexity again. "This runs in O(n log n) time and O(n) space."
- Mention what you'd add with more time: tests, error handling, optimization.

## Common interview formats and how to handle each

### Live coding / SQL / live querying

- Use the language / dialect you're strongest in unless told otherwise.
- Don't optimize prematurely. Get a working solution first, then improve.
- Comment your code as you write — short, semantic. Helps the interviewer follow and helps you when you re-read.
- If you're given a real environment (LeetCode, HackerRank, a notebook), use it. Run small tests early.

### Take-home assignments

Take-homes optimize for clarity and judgment over raw speed.

- **Read the prompt twice.** Note the explicit and implicit asks.
- **Spend 20% of your budget on planning** before any work.
- **Cap your time.** If they say 4 hours, spend 5 max. Diminishing returns are real and writing "spent ~5 hours" honestly is fine.
- **Document decisions, not code.** A clean README explaining tradeoffs (what you tried, what you chose, what you'd do with more time) is the differentiator.
- **Make it reproducible.** Single-command run if possible. Pinned dependencies. Sample data included or downloadable.
- **Showcase one extra thing.** A small visualization, a unit test, a sensitivity analysis. Not five extras — one extra, polished.

### Whiteboard / system design / architecture (for senior or specialized roles)

For new grads, this is rarer but does happen for some technical tracks. The shape:

- Clarify scope, scale, success metric.
- Sketch high-level components.
- Drill into the 1–2 components the interviewer is curious about.
- Mention tradeoffs at every choice point.
- Don't try to design Twitter. Design a slice of it that you can defend.

### "Walk me through your project"

Half-technical, half-behavioral.

- Pick the right project for the audience. (For an analytics role, the analytics project — not the React app.)
- Frame: problem → constraints → your approach → outcome → what you'd do differently.
- Be ready for "why this approach and not X?" Have at least one alternative you considered and rejected.
- Be ready for "what was the hardest part?" Have a real answer with a real tradeoff.

## When you're stuck

Three escalating moves:

1. **Re-state what you know.** "Okay, what I have so far is… The next thing I need is…" Often the act of summarizing unblocks you.
2. **Try a smaller / dumber version.** Brute force first. A working O(n²) beats a broken O(n).
3. **Ask a directed question.** Not "I'm stuck." Try: "I'm considering between A and B — A handles X better but B might be simpler. Which direction would you push on?"

Interviewers are usually willing to nudge if you've shown effort. Use that.

## When you finish early

Don't sit silently. Options:

- "Want me to walk through edge cases?"
- "Want me to discuss complexity tradeoffs?"
- "I could refactor this for readability — want to see that, or move on?"
- "I noticed [related question] — happy to think through that too."

Self-direction is signal.

## Demonstrating agency (the differentiator)

"Agency" is the single biggest signal at top firms — interviewers literally write "high agency" or "would ship without being told" in offer-leaning debriefs. Most new-grad candidates leave it on the table because they're trying not to seem presumptuous.

Concrete moves that show agency in a technical loop:

- **Bring a small artifact you weren't asked for.** A 1-page teardown of their public product, a small reproduction of their public dataset, a sketch of how you'd approach the role's first 30 days. Casual delivery: "I had time this morning so I sketched this — happy to walk through if you want."
- **Steer the interview when they leave space.** "I have a couple of directions I think would be most useful — want me to walk through the project, or jump to the technical question first?"
- **Name what you'd do next.** After finishing a problem: "If I were doing this in production, I'd add tests for X, monitoring for Y, and revisit Z if data volume 10xed." Shows you think past the interview window.
- **Send a follow-up that *does* something.** Not just a thank-you — a 2-paragraph extension of a discussion point. "You mentioned the team's debating X. I thought about it more — here's where I land and the tradeoff I'd flag."

These moves are small, low-risk, and they completely separate offer-winning candidates from passable ones.

## Mistakes that quietly fail you

- **Going silent.** You got the right answer but interviewer can't tell how. Inconclusive ≈ no-hire.
- **Starting to code immediately.** Looks fast, costs you the clarification phase.
- **Arguing with the interviewer.** They're sometimes wrong, but the move is "interesting — can you walk me through what you're seeing?", not "no, you're wrong."
- **Overclaiming.** Saying you know X then fumbling. Better: "I've used X a couple of times — happy to take a swing if you'd like."
- **Forgetting to test.** "I think it works" without verifying loses points even if it works.
- **Refusing hints.** Interviewers offer hints to help you succeed. Take them.

## Practice protocol

- **Daily 30-min drill** in your weakest medium (SQL, coding, statistics, Excel) for 3–4 weeks before peak interview season.
- **Mocks > solo grinding.** Schedule 2 mock interviews per week with peers ahead of major loops.
- **Re-do problems you got wrong.** A week later. Then a month later. Spaced repetition works.
- **Build a "fumbles" doc.** Every time you blank in a real interview, log the question and the answer you wish you'd given. Read before the next one.

## Topic checklists (use to find your gaps before drilling)

You can't drill what you can't name. Use these as a self-audit. Cover the topics relevant to your target role.

### Coding / DSA (engineering, ML, some data roles)

- Arrays, strings, hash maps, sets — most warm-up problems live here.
- Two pointers, sliding window.
- Recursion, backtracking.
- Trees (BST, traversals, DFS/BFS), graphs (BFS/DFS, topological sort, shortest path).
- Heaps / priority queues.
- Dynamic programming — at minimum 1D and 2D, memoization vs. tabulation.
- Sorting + binary search variants.
- Big-O: time and space, in your sleep.

### SQL (data, analytics, BI, some PM/strategy roles)

- Joins (inner, left, full, anti, self), and when each is right.
- Aggregations + GROUP BY + HAVING.
- Window functions: ROW_NUMBER, RANK, LAG/LEAD, running sums, partitioned aggregations.
- CTEs and subqueries — when each is cleaner.
- Date/time arithmetic, cohort framing, day-over-day or week-over-week math.
- NULL handling (the silent killer of many SQL solutions).
- Common patterns: top-N per group, retention/cohort, funnels, sessionization, gaps and islands.
- EXPLAIN / query plans (mostly for senior roles, but be aware they exist).

### Statistics + experiment design (data, ML, PM)

- Descriptive stats; skew and outliers.
- Sampling, sampling bias, central limit theorem at an intuitive level.
- Hypothesis testing: nulls, p-values, type I/II errors, what they actually mean.
- A/B test design: power, MDE, run-length, peeking, stratification.
- Correlation vs. causation; confounders; Simpson's paradox.
- Common pitfalls: novelty effects, survivorship bias, selection bias.

### Modeling / ML (ML, applied data science roles)

- Linear and logistic regression — assumptions, interpretation.
- Bias-variance, regularization, cross-validation.
- Tree-based models (random forests, gradient boosting); when they beat linear.
- Classification metrics: accuracy/precision/recall/F1, ROC/AUC, calibration.
- Regression metrics: MAE/RMSE/MAPE; when each matters.
- Imbalanced classes, class weights, sampling strategies.
- Feature engineering basics; leakage detection.
- Model evaluation in production vs. offline (drift, monitoring).

### Excel / spreadsheets (BA, finance, ops)

- VLOOKUP / XLOOKUP / INDEX-MATCH; pivot tables; power query at a basic level.
- Dynamic ranges, structured references, conditional aggregations (SUMIFS, COUNTIFS).
- Light financial modeling: NPV, IRR, payback, scenario tables.
- Charting clearly — when bar vs. line vs. scatter, when to skip the chart.

### Domain reasoning (case-style, applies to most roles)

- Funnels, conversion rates, retention, LTV/CAC.
- Unit economics for the industry you're targeting.
- Common metric definitions (DAU/MAU, ARPU, NPS, CSAT, NRR — depending on role).

## Where to drill

- **LeetCode** for algorithms. Easy + medium are most of new-grad questions. Skip hard until you've solved a healthy number of mediums.
  - **NeetCode 150 / NeetCode roadmap** is a structured starting list — it's what most people use to learn the patterns rather than grinding random problems.
  - **Pay attention to company-tagged questions.** The LeetCode "Company" filter (or sites like LeetCode-Discuss, Glassdoor) lists problems recently asked at specific companies. Interviewers often pull from a small pool — drilling the last 6 months of company-tagged mediums is high-ROI before a specific loop.
- **StrataScratch / DataLemur / SQLZoo** for SQL. Drill window functions deliberately — they're the biggest separator. DataLemur leans interview-flavored, StrataScratch leans real-company problems.
- **StatQuest (YouTube)** for stats fundamentals — the explanations are unusually clear. *Naked Statistics* (Wheelan) is a friendly book on the same material if you prefer reading.
- **Pramp / Interviewing.io** for paired live mocks.
  - *Honest caveats:* Pramp's matchmaking is uneven and partner no-shows are common (book extra slots). Quality of feedback depends heavily on the partner's experience. Use it for cold-start volume, not for polish.
  - **Schedule peer mocks too.** A classmate or alum 1–2 years ahead who's done your target role's interview will give better signal than a random Pramp partner.
- **Real take-homes from public sources** — companies sometimes post sample take-homes; specific GitHub repos collect them (search "data-science-take-home"). Kaggle competitions can mimic the format but tend to overfit to leaderboard tricks.

Set a daily floor (30–45 min for 4–6 weeks before peak loops) over a sprint (4 hours every Saturday). Consistency wins; cramming doesn't.

## Know which platform a company uses

Companies tend to use one assessment platform consistently. Knowing it ahead of time saves you from fighting unfamiliar UI on the day:

- **HackerRank** — common at finance, enterprise, and many large tech companies.
- **CoderPad / CodeSignal** — common at growth-stage and mid-size tech, also used by senior loops at FAANG-tier.
- **Codility** — common at European companies and some US enterprises.
- **Karat** — third-party live interviewing service used by several big tech companies for first-round technical screens.
- **Internal company tools** — many large companies have proprietary platforms (Google's, Meta's, Amazon's). Layout matters less than knowing it'll be plain.

Ask the recruiter what platform will be used. They'll tell you. Spend 20 minutes the day before clicking around the demo / sandbox.

## What to bring / set up before a virtual interview

- Stable internet. Hardwired or strong wifi. Phone hotspot as backup.
- Plain background. Decent lighting (window facing you, not behind you).
- Webcam at eye level. Mic that isn't your laptop's built-in if possible.
- Browser tabs closed except: the meeting, the platform (LeetCode, etc.), a doc with your story bank and notes, the JD.
- Water, paper, pen.
- Test the platform 30 minutes before. Login issues mid-interview are a real thing and a real disaster.

For async video interviews (HireVue and similar), see doc 12.

## Mixed in-person + remote panels

A growing format: some interviewers in a conference room, others remote. Two practical adjustments:

- **Address the camera, not just the room.** Remote interviewers get less of you by default.
- **Repeat names when responding.** "To Priya's question…" — helps the remote folks follow.
- **Don't whisper to the in-room people.** What looks casual to you reads as exclusionary to the remote panelist.
