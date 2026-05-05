# Pyramid principle (SCQA) frame

Lead with the answer. Build a logical tree underneath where each level is MECE (mutually exclusive, collectively exhaustive). The reader can stop reading at any level and still walk away with a coherent picture.

This frame is attributed to Barbara Minto's work at McKinsey. The shape: one top claim, supported by 2-4 grouped arguments, each backed by evidence. The opener is SCQA - Situation, Complication, Question, Answer.

## When to use this frame

Best fit: leadership memos, board decks, exec readouts, time-pressured reviewers who skim the first paragraph and decide whether to read further. Use it when you need a clean yes/no decision, when the audience trusts your judgment and wants the recommendation up front, or when the doc has to survive being forwarded with no preamble. The pyramid forces you to commit to a position and defend it, which is what an executive reader is paying for.

Bad fit: collaborative design discussion where the team needs to participate in the reasoning, exploratory ideation where you don't yet have a recommendation, contexts where alignment depends on showing your work, or audiences who will reject a top-down conclusion if they haven't seen the inputs. If the reader needs to think alongside you, use a different frame - the pyramid will read as presumptuous.

## Author template

### Opening - SCQA (four short paragraphs)

**Situation.** *State what we already agree on. The shared baseline. No new claims, no surprises - just the context the reader would nod along to.*

[placeholder for situation]

**Complication.** *What changed, what's broken, or what new evidence has surfaced that makes the situation no longer stable. This is the load-bearing paragraph - if there's no real complication, there's no reason for the doc to exist.*

[placeholder for complication]

**Question.** *The implicit question the complication raises. Usually one sentence. Often "what should we do?" but be specific - "should we keep investing in X, pause, or wind it down?"*

[placeholder for question]

**Answer.** *The recommendation, in one sentence. This is the top of the pyramid. Everything below this point exists to support this sentence.*

[placeholder for answer]

### The pyramid

```
                    [Recommendation - one sentence]
                              |
        --------------------------------------------
        |                     |                    |
   [Argument 1]          [Argument 2]         [Argument 3]
        |                     |                    |
   - evidence 1a          - evidence 2a        - evidence 3a
   - evidence 1b          - evidence 2b        - evidence 3b
   - evidence 1c          - evidence 2c        - evidence 3c
```

**Recommendation:** [one sentence, declarative, no hedging]

**Supporting arguments (2-4, MECE).**

MECE means the arguments don't overlap and together they cover the full case for the recommendation. Overlap example to avoid: "the platform is slow" and "users are churning because of latency" - these are the same point in different words, not two arguments. A MECE split of the same territory might be "the system can't meet its current SLO" (technical) and "customers have escalated three times this quarter" (commercial).

- **Argument 1: [claim].** *Should independently support the recommendation. If you deleted arguments 2 and 3, this one alone should make the case plausible.*
  - Evidence 1a: [specific, verifiable fact, number, or quote]
  - Evidence 1b: [specific, verifiable fact, number, or quote]
  - Evidence 1c: [specific, verifiable fact, number, or quote]

- **Argument 2: [claim].** *Different territory from argument 1. No overlap.*
  - Evidence 2a: [specific, verifiable fact, number, or quote]
  - Evidence 2b: [specific, verifiable fact, number, or quote]
  - Evidence 2c: [specific, verifiable fact, number, or quote]

- **Argument 3: [claim].** *Different territory from arguments 1 and 2. Together with them, the set covers the full case.*
  - Evidence 3a: [specific, verifiable fact, number, or quote]
  - Evidence 3b: [specific, verifiable fact, number, or quote]
  - Evidence 3c: [specific, verifiable fact, number, or quote]

If you find yourself reaching for a fourth or fifth argument, stop and check whether two of them are actually the same point. More than four top-level arguments is almost always a sign of weak grouping.

### Optional sections (use sparingly)

- **Risks and what would change our mind.** Two or three failure modes and the signal that would make us revise the recommendation.
- **Decision asked.** One sentence naming the decision, the decider, and the deadline.

## Reviewer pass

Read the doc once at speed, then ask:

- Is the recommendation in the first sentence of the answer paragraph? If the reader stopped after the SCQA, would they know what we're recommending?
- Are the supporting arguments MECE? Specifically: is there any overlap between argument N and argument M (same point, different wording)? Is there an obvious counter-argument or territory the set doesn't cover?
- Does each argument independently support the recommendation? If you deleted any one of them, does the recommendation still stand on the others, or does the case collapse?
- Would the doc collapse cleanly to a single page if we cut everything below level 2 (i.e., kept only SCQA, recommendation, and the argument headlines)? If not, the headlines aren't doing their job.
- Is the SCQA "complication" load-bearing, or is it manufactured? Specifically: would a reader who knows this domain agree something genuinely changed, or does the complication read as a setup written backwards from the recommendation?
- Does the evidence under each argument actually support that specific argument? Or is some of it generic context that could sit under any argument? Generic evidence is a sign the argument is too vague.
- Is the recommendation defensible without the framing? Strip the SCQA - does the pyramid still hold?
- Did anything important get cut to fit the structure? The pyramid is a tool for clarity, not for hiding inconvenient facts.

## Anti-patterns specific to this frame

- **Recommendation buried at the end.** "After considering X, Y, and Z, we recommend ..." - this is a chronology, not a pyramid. Move the recommendation to sentence one.
- **Overlapping arguments.** Two arguments that say the same thing in different words. The set isn't MECE. Collapse them or re-cut the territory.
- **Evidence that doesn't support its argument.** Evidence filed under argument 2 that's actually about argument 1, or generic context that could be filed anywhere. If the evidence doesn't move the specific claim above it, it's filler.
- **Manufactured complication.** SCQA where the "complication" is invented to justify a recommendation the author already wanted. Reader test: would a peer who didn't co-write the doc agree that something genuinely changed?
- **Pyramid that's actually a chronology.** Arguments ordered by "first we tried A, then we tried B, then we landed on C." That's a story, not a pyramid. Re-cut by claim, not by timeline.
- **More than four top-level arguments.** Almost always a sign of weak grouping - two or three of them collapse into one if you re-cut the territory.
- **Hedged recommendation at the top.** "We could consider potentially exploring ..." - the top of a pyramid is a declarative sentence. If you can't commit to a position, you're not ready for this frame.
- **Pyramid without a question.** SCQA where the Q is missing or vague. Without a sharp question, the answer has nothing to anchor to and the arguments drift.
- **Evidence that's all qualitative or all quantitative.** Single-mode evidence under every argument is a tell that the author hasn't triangulated. Mix where the territory allows.
