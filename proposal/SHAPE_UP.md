# Shape Up frame

A frame for shaping, pitching, and betting on work in fixed time with variable scope. Drawn from Ryan Singer's Shape Up at Basecamp. Fix the time, vary the scope. The pitch sets an appetite and a shaped problem with rough boundaries, not a detailed spec. The team gets full autonomy within the appetite. If the work won't fit, the pitch is reshaped or killed - scope does not sprawl.

## When to use this frame

Best fit: feature work with elastic scope and a clear customer problem. Anything where you can credibly answer "if we run out of time, what do we cut?" with something other than "nothing." Examples in our world: a connector improvement, a workflow that customers ask for in different shapes, a UI surface that has many possible depths. The frame works because the team can trade off polish, edge cases, and adjacent niceties to land the core within the appetite.

Bad fit: hard-deadline regulatory work (the deadline drives scope, not the appetite), exploratory research with no defined end state (no shape to bet on), ongoing operations and on-call (no cycle boundary), and infrastructure work where scope is mostly fixed by the system you're integrating with (you can't trim half a migration). For those, use a different frame.

## Author template

Copy the section below into your pitch doc. Each italic prompt is a question to answer, not a heading to keep.

### Problem

*One specific situation where someone hit the wall. Not "users struggle with X" - the actual moment, the actual user, the actual workaround they're using today. If you can't name a specific instance, you haven't shaped the problem yet, you've named a theme.*

[describe the raw demand: who, what they were trying to do, where it broke, what they did instead]

### Appetite

*How much is this problem worth to us right now? Pick one and commit.*

- Small batch: 2 weeks, 1-2 people
- Big batch: 6 weeks, 1-3 people

[state the choice and one sentence on why this size is honest - what makes this worth two weeks but not six, or six but not a quarter]

### Solution sketch

*Describe the shape of the work in words. What would you draw with a fat marker on a whiteboard? Boxes, arrows, the flow between states. Not pixels, not field-level specs, not component names from the design system.*

[the elements: what new pieces exist, what they connect to, what the user moves through]

[the flow: the path from the trigger to the resolution, in 3-6 steps]

[what would be drawn fat-marker: list the 2-4 sketches that would accompany this pitch on a whiteboard, by name. e.g. "the entry point", "the in-progress state", "the failure path"]

### Rabbit holes

*The 3-5 specific risks that could swallow the cycle, each with a response baked in. Not "performance might be hard" - which performance, on which path, and what's the answer. If you can't write the response, the rabbit hole isn't shaped, and you should keep shaping before betting.*

- [risk 1]: [the response - either the constraint we accept, the simplification we'll take, or the bound we'll hold]
- [risk 2]: [response]
- [risk 3]: [response]

### No-gos

*What we are explicitly not doing inside this appetite. Each item should be a thing a reasonable reader would otherwise expect to be in scope. Generic exclusions ("not solving world hunger") don't earn their place.*

- [scope item we're not touching, with one line on why it's out]
- [scope item we're not touching, with one line on why it's out]
- [scope item we're not touching, with one line on why it's out]

## Betting table format

At the betting table, 2-4 shaped pitches go side by side. The point is comparison, not pitching one in isolation. Appetite is the comparable axis - everything else flexes.

| Pitch | Problem (one line) | Appetite | Core risk | Why now |
| --- | --- | --- | --- | --- |
| [pitch 1 name] | [one specific situation] | small / big | [the rabbit hole most likely to bite] | [what changed that makes this worth betting on this cycle] |
| [pitch 2 name] | [one specific situation] | small / big | [the rabbit hole most likely to bite] | [what changed] |
| [pitch 3 name] | [one specific situation] | small / big | [the rabbit hole most likely to bite] | [what changed] |

Rules of the table:

- Each pitch has been shaped (problem, appetite, sketch, rabbit holes, no-gos) before it gets a row. Unshaped ideas don't bet.
- A "no" at the table is not a backlog entry. It's a no for this cycle, and the pitch may or may not return - it is not guaranteed a slot later.
- The bettors leave with a small set of bets, each with an owner and a circuit breaker (the cycle ends when the cycle ends).

## Reviewer pass

Questions to ask of any Shape Up pitch before betting on it. Each one targets a known failure mode of this frame.

- Is the appetite credible, or is it a deadline in disguise? An appetite says "this problem is worth N weeks to us." A deadline says "this must ship by date X." If the answer to "what if it takes longer?" is "we'd extend," the appetite isn't real - it's a target with a soft floor.
- Are the rabbit holes named with specific responses, or just listed? "Scaling could be tricky" is a list. "Beyond 10k rows we degrade to async, accepted" is a response. If the rabbit holes section reads like risks on a status report, it isn't doing its job.
- Is the solution shaped or speced? Shape: the boxes, the flow, the boundaries. Spec: the field names, the API shape, the component tree. If the pitch removes the team's autonomy on implementation, it's a spec wearing a pitch's clothes.
- Is the no-gos section doing real work to prevent scope creep, or is it generic? Each no-go should be something a reasonable reader would otherwise assume is in scope. If you can delete a no-go without anyone noticing, it wasn't earning its place.
- Is the problem one specific situation, or a vague theme? "Users want better search" is a theme. "When a customer with 50k assets filters by owner and source, the result list takes 14 seconds and they give up" is a situation. The pitch should anchor on the second.
- Does the appetite match the shape? Big appetites for small problems and small appetites for big problems are both shaping failures. If the team would feel cramped in the appetite, the pitch is too big. If they'd coast, the appetite is too generous.
- If we run out of time at week N, what do we cut? If the answer is "nothing, it all has to land," the scope isn't elastic and Shape Up isn't the right frame.

## Anti-patterns specific to this frame

- **Appetite as deadline in disguise.** The pitch says "6 weeks" but the team knows that if it slips, it slips. The frame breaks the moment the appetite is negotiable mid-cycle. The whole point is that the appetite is the constraint and the scope flexes around it.
- **Fat-marker sketches that are actually wireframes.** If the sketch shows pixel layouts, font sizes, or specific component choices, the team has lost the autonomy the frame is meant to give them. Fat-marker means a reader can tell what flows where, not what it looks like.
- **Empty or generic rabbit holes.** "We might hit perf issues" with no response. "Auth could be tricky" with no response. A rabbit hole without a baked-in response is a known unknown the cycle will eat.
- **Scope that grows mid-cycle without reshaping.** A bet was placed on a specific shape. If new requirements arrive mid-cycle, the right move is either a new pitch for next cycle or a reshape and rebet, not silent expansion of the current cycle.
- **Pitch that reads like a backlog ticket.** "As a user, I want to filter by X so that Y" is not a pitch. A pitch has a specific situation, an appetite, a shape, rabbit holes, and no-gos. If the document fits in a Jira description, it hasn't been shaped.
- **Multiple pitches with the same appetite and no comparison.** The betting table is for comparison. If all three pitches are big-batch and there's no axis on which they trade off, the table is a rubber stamp, not a decision.
- **Shaping that runs as long as the cycle.** Shaping happens before the cycle, on a separate track, by a different group. If shaping bleeds into building, the team starts the cycle with an unshaped pitch and the appetite becomes fiction.
- **No-gos that are obvious.** "We won't redesign the entire product" is not a no-go, it's a tautology. Real no-gos cut adjacent work that a reader would otherwise expect to be in scope.
