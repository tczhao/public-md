# PR/FAQ frame

The Amazon "working backwards" approach. You write the launch as if it already shipped - a one-page mock press release in customer language - then a FAQ that confronts the hardest internal and external questions. The proposal succeeds if the press release is one a customer would actually want to read. Customer benefit gets articulated before any internal justification.

## When to use this frame

Best fit: customer-facing launches, new products, pricing or packaging changes, public APIs, anything an external audience will see and react to. The frame forces you to lead with the customer outcome, which is exactly the muscle these initiatives need. If you cannot write a plausible press release, the idea probably is not ready to ship.

Bad fit: internal infrastructure, developer tooling with no external surface, refactors, migrations, organizational changes, anything where the audience is internal and the value is operational. Forcing a press release on these produces theatre. Use the generic proposal frame or SDR instead.

## Author template

### Part 1: the mock press release

Keep this to one page. Customer language only. No internal jargon, no roadmap codenames, no acronyms a journalist would not know.

#### Headline

_One line. Carries the news. A reader who only sees the headline should know what shipped and why it matters. Avoid generic verbs like "announces" or "introduces" without an object that lands. Bad: "[Company] announces platform update." Good: states the specific change and the specific outcome._

#### Subhead

_One sentence. Names the customer and the concrete benefit. If the headline is the what, the subhead is the who and the so-what._

#### Location and date

_[City, Date] - placeholder. Use the planned launch date, not today._

#### Opening paragraph

_2-3 sentences. Restate the news in plain prose. Who is announcing what, for whom, available when. A reader who stops here should still walk away with the core claim._

#### Customer problem

_One paragraph. The pain in the customer's words. Be specific about who feels it (role, team, company shape) and what it costs them today. Resist the urge to describe the problem in terms of your product's absence - describe it in terms of the customer's day._

#### Solution

_One paragraph. How the thing works, from the customer's seat. What they do, what they see, what changes. Mechanism over feature list. No internal architecture._

#### Customer quote

_One imagined but plausible quote from a named-style placeholder customer (e.g. "[Title] at [Company shape]"). It must sound like a real human describing a real change in their work. Specific verb, specific outcome. If you cannot imagine a real person saying it out loud without cringing, rewrite it. No marketing adjectives in the quote._

#### Internal exec quote

_One quote from an internal leader. It should be a specific commitment or a specific point of view, not a brand statement. "We are excited to..." is a fail. "We built this because [specific belief about the customer or the market]" is the shape._

#### Three concrete benefits

_Three bullets. Each one names a measurable or observable change for the customer. Use placeholder magnitudes like "[X% reduction in Y]" rather than fabricating numbers. If you cannot articulate three distinct benefits without overlap, you have one or two, not three - say so._

- [Benefit 1: concrete change for the customer]
- [Benefit 2: concrete change for the customer]
- [Benefit 3: concrete change for the customer]

#### Availability and pricing

_One line. When customers can get it, on what plans, at what price shape. "Generally available [date]" or "in private preview for [segment]" - whichever is honest._

### Part 2: the FAQ

Five to ten questions total, split across the two audiences. Pick the questions that are genuinely hard - if every question has a comfortable answer, the FAQ is not doing its job.

#### External FAQ

_Questions a journalist, analyst, or prospective customer would ask. Frame each in their voice, not yours._

- **[Question a journalist would ask about scope or differentiation]**
  _Answer in customer language. No internal jargon. Honest about limits._
- **[Question a customer would ask about migration, lock-in, or what they have to change]**
  _Answer with the actual switching cost, not a downplayed version._
- **[Question about pricing, packaging, or who this is not for]**
  _Name the segment this is not aimed at. Saying "everyone" is a tell._
- **[Question about security, data handling, or compliance posture]**
  _Specific posture, not a gesture toward a trust page._

#### Internal FAQ

_Questions a skeptical PM, engineer, or finance partner would ask in a review. The harder the question, the more this section earns its place._

- **[What breaks or gets harder for existing customers / existing systems]**
  _Name it. If nothing breaks, explain why with specifics._
- **[What this costs to build and to run, and how that compares to the expected return]**
  _Order-of-magnitude is fine. "TBD" is not._
- **[What the riskiest assumption is, and how we will know if it is wrong]**
  _One assumption, one signal, one threshold._
- **[Why now, and why us - what changed that makes this the right time]**
  _If the answer is "leadership asked for it," say so and stop pretending otherwise._
- **[What we are explicitly not doing in v1, and why]**
  _The cut list is the proposal. Without it, scope is undefined._

## Reviewer pass

Run these checks against the draft. Each one is a kill criterion - if the answer is wrong, the draft goes back, not forward.

- Would a real customer want to read this if it landed in their inbox? Read the PR out loud. If it sounds like a release-notes entry or a feature changelog, the news is not landing.
- Does the headline carry the news? Cover the subhead and the body. If the headline alone leaves the reader guessing what shipped, rewrite it.
- Is the customer quote plausible? Read it as if a real person said it on a call. If it sounds like a marketing puppet ("the platform has transformed how we operate"), it is not a quote, it is filler.
- Is the exec quote a specific commitment or a brand statement? "We believe data teams deserve better" is a brand statement. "We built this because [specific belief about how customers actually work]" is a commitment.
- Does the FAQ dodge the hard questions? Cost, security, migration, what breaks, who this is not for, what we are not doing - if any of these are missing or softened, the FAQ is incomplete.
- Is the PR using internal jargon? Codenames, team names, acronyms, internal product terms. Strip them all. If a journalist would have to ask what a word means, it does not belong.
- Are the benefits distinct, or are they three phrasings of the same thing? Three bullets that all reduce to "it is faster" is one benefit, not three.
- Are the numbers in the PR real, placeholder, or fabricated? Placeholders are fine. Fabricated stats are a fail and will leak into the actual launch if not caught here.
- Is the availability line honest? "Coming soon" without a date is a tell that the team does not know when it ships.
- Could a competitor write a near-identical PR by changing the company name? If yes, the differentiation is not in the draft.

## Anti-patterns specific to this frame

- **Fake stats in the PR.** Inventing "73% faster" or "$2M saved" to make the draft feel concrete. Use bracketed placeholders until real numbers exist.
- **Marketing adjectives in customer quotes.** Robust, seamless, powerful, game-changing, world-class, next-generation. No human says these out loud. Strip them.
- **FAQ that only includes softball questions.** "How does this help customers?" is not a hard question. The FAQ exists to confront the questions you would rather not answer.
- **PR that reads like a release-notes entry.** A list of capabilities with verbs in front. The PR should describe a change in the customer's world, not a list of things the product can now do.
- **Exec quote as brand statement.** "At [Company], we believe..." Anything that could be lifted unchanged into a different launch is not a real quote.
- **"We are excited to see what you'll build" closings.** Or any variant. Cut.
- **Internal jargon leaking into the PR.** Codenames, team names, internal acronyms, project numbers. The PR is for an external audience.
- **Headline that announces a thing instead of news.** "[Company] announces [Product]" with no specific outcome in the line. The headline should survive standalone.
- **FAQ questions written in your voice instead of theirs.** External questions should sound like a journalist or customer asked them. If every question sounds like a PM wrote it, rewrite.
- **Skipping the cut list.** No "what we are not doing in v1" entry. Without it, the scope is whatever the loudest stakeholder wants on the day of launch.
- **A PR for an internal initiative.** If the audience is internal, this frame is the wrong tool. Use a different frame.
