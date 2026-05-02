# 12 — AI and the Modern Hiring Process

The hiring process changed substantially in 2024–2026. Resume screeners are now LLM-powered, async video interviews are common, take-homes are gated by AI-use policies, and recruiters can detect AI-generated cover letters. This doc covers what changed and how to adapt without crossing ethical lines.

## What's actually changed

- **Resume screening is LLM-augmented.** Most large-company ATSes now run an LLM pass after keyword matching. They're more forgiving of formatting but more critical of vague claims and inconsistent dates.
- **Async video interviews** (HireVue, Modern Hire, Karat) are standard at the early funnel for many large employers. You're alone with a camera and a timer.
- **Take-home assessments** increasingly include explicit AI-use policies — sometimes "AI is allowed, document what you used," sometimes "no AI tools," sometimes monitored via screen recording.
- **Recruiters routinely run AI-detection** on cover letters and outreach messages. Generic-LLM-flavored writing is filtered down or out.
- **AI-on-AI** is a real phenomenon: candidates use AI to mass-apply, recruiters use AI to mass-screen and respond. The signal-to-noise has crashed. Quality + relationship is the only durable edge.

## How to use AI in your search (ethical playbook)

AI is a force multiplier when used as a thinking partner. It's a liability when used as a ghostwriter for things that are supposed to reflect your own voice.

### Use it for

- **Brainstorming.** Generating 20 STAR story angles for a single experience, then picking the best.
- **Mock interviewing.** Have it role-play a tough interviewer. Ask it to grade you on the rubric in doc 04.
- **Summarizing prep.** Compressing a 30-page company report into 1 page of key facts.
- **Practicing your translation skills.** "Take this technical project and explain it to a marketing director." Compare its version to yours.
- **Editing your own writing for clarity** — your draft, edited tighter. Not its draft pretending to be yours.
- **Generating practice problems.** "Give me 10 SQL window-function problems at intermediate difficulty."
- **Researching companies.** Pulling org structure, recent product launches, leadership backgrounds (verify everything — AI hallucinates names and titles).

### Don't use it for

- **Writing your cover letter from scratch.** Recruiters can tell, and the homogenized voice loses you the human angle the cover letter exists for.
- **Mass-applying via auto-applier tools.** Companies blacklist domains and signatures associated with these. The fake "personalization" is obvious.
- **Take-home assignments with explicit no-AI policies.** Honor the policy. Many companies ask in the follow-up interview to walk through your code line by line — you'll be exposed.
- **Live interview answers.** Reading from a hidden window is detected by experienced interviewers (eye flicks, latency, vocabulary shifts). Even when not detected, it eliminates your ability to handle the follow-up question that probes your actual understanding.
- **Inflated resume bullets.** "Architected a scalable distributed system" for a course project will be torn apart in the technical interview.

### The ethical line

Ask: "If I told the interviewer exactly how I used AI on this, would they be fine with it or annoyed?"

- "I used Claude to generate practice questions and grade my answers." → fine.
- "I used Claude to draft a first cover letter, then heavily rewrote it." → usually fine.
- "I used Claude to write my take-home from scratch and submitted it." → not fine.
- "I had Claude listening to my interview through a second device, generating answers I read aloud." → career-ending if found.

When in doubt, default to the conservative interpretation.

## Beating LLM resume screeners

The LLM pass is looking for *coherence* between the role and your resume, not just keyword matches. Two practical implications:

1. **Tailor each resume to the JD's actual language.** The LLM is comparing semantic similarity, not just exact strings. If the JD says "stakeholder communication" and you say "client management," the LLM gets it — but only if "client management" is in a context that makes sense for the role.
2. **Make your top 3 bullets unambiguous.** The LLM weights early bullets heavily. Bury the strongest there, with quantified outcomes.

What still doesn't work: keyword-stuffing in white text, hidden boxes, footer keywords. Modern parsers strip these and many flag them.

## Async video interviews (HireVue and similar)

You log in, get a question, get 30 seconds to think, then 1–3 minutes to record. You usually get 2–3 takes per question, sometimes 1. Common at large enterprises for early-funnel screening.

### Setup

- **Hardwired internet** if at all possible.
- **Wired headphones with mic** beat laptop audio 10/10 times.
- **Lighting in front of you**, not behind. A window or ring light. Not the ceiling fan.
- **Camera at eye level.** Stack books under your laptop.
- **Plain wall background.** Not a virtual background — they glitch around your edges and look weird.
- **Test the platform** the day before with a "practice question." Most platforms offer this.

### Performance

- **Treat the camera lens as the interviewer's eyes.** Not the screen.
- **Smile at the start of the answer**, even briefly. Sets warmth that the recording can't read otherwise.
- **Stand up if it helps energy.** Some candidates do — laptop on a high counter.
- **Speak ~10% slower** than feels normal. Recorded video plays back faster psychologically.
- **Don't try to fill the full time.** A tight 90-second answer beats a flabby 3-minute one.
- **Restart fearlessly within the take limit.** First 5 seconds of mumbling? Stop, restart. The platform won't penalize a clean restart.

### What they're scoring

Some platforms use AI scoring layered with human review; some are human-only. Either way, the signal they're looking for is similar to a live interview: clarity, structure, specifics, energy. Don't optimize differently for the algorithm.

## AI-monitored coding assessments

Some platforms record your screen, webcam, and audio during a take-home or live coding test. They flag tab switching, copy-paste from external sources, and unusual idle times.

- **Read the policy first.** Some allow Stack Overflow and docs. Some allow LLM tools explicitly. Some forbid both.
- **Document what you used** if the policy permits AI but asks for disclosure.
- **Don't do anything you wouldn't do live.** If they invite you back to a follow-up, expect to walk through the code.

## Cover letters in the AI era

The point of a cover letter shifted. It's now one of the few signals that you're actually human and actually invested. A clean, specific, slightly imperfect human cover letter beats a polished LLM one almost every time.

If you use AI:

- Use it to *react to your draft*, not to produce one.
- Read the result aloud. If it doesn't sound like you, rewrite the parts that don't.
- Cut adjectives. LLM cover letters love adjectives. Yours shouldn't have many.

## Recruiter outreach via AI

Some recruiters now use LLM-generated outreach at scale. Often you can tell. Equally, recruiters can tell when *you're* using it.

Signal that you wrote it yourself:

- A specific reference to something only-you-would-notice (a comment from their podcast appearance; a project on their GitHub).
- An unusual but coherent sentence rhythm.
- One concrete number, name, or detail that AI is unlikely to invent.
- A small imperfection (a casual aside, an honest "I might be wrong about X").

These are noise to a fluent generator and signal to a human reader.

## What this means for your prep

- **Practice translating** technical depth into specific stories. AI-generated answers are generic, so the differentiated signal is *real specificity*.
- **Do mocks with humans, not just LLMs.** Humans get bored, distracted, surprised, charmed — LLMs don't replicate any of these reactions.
- **Build artifacts that are obviously yours.** A weird side project, a public writeup, a niche tool. Anything the AI couldn't have produced for you.
- **Treat your unfair advantage as your humanity.** Specifics, weirdness, tradeoffs, opinions. That's what gets remembered in a sea of well-written-but-bland applications.
