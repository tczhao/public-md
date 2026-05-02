# 02 — Online Presence

After your resume, the recruiter Googles you. They open three tabs, in this order: LinkedIn, GitHub (if technical) or portfolio (if creative/analytical), and a general search of your name. Make those three tabs work for you.

## LinkedIn

LinkedIn is the highest-ROI online surface. It is also where most new grads quietly under-invest.

### Profile checklist

- **Photo.** Plain background, head and shoulders, neutral expression with a small smile, business casual minimum. Phone selfies are fine — natural light by a window.
- **Banner.** Generic but on-theme (stock skyline, abstract). Avoid the default blue.
- **Headline.** Not your job title. The formula `[Target role] | [proof points] | [school]` is the floor, but it's also generic — recruiters scroll past hundreds. Better headlines do one of: name a specific outcome, name a specific tool combination not everyone has, or name a niche you actually care about. Compare:
  - Generic: `Aspiring Data Analyst | SQL · Python · Tableau | NYU '26`
  - Sharper: `Marketing analytics intern → full-time | SQL + dbt + Looker | NYU '26`
  - Sharper: `Built churn models for a fintech this summer · Python / SQL · open to data analyst roles · NYU '26`
- **About.** 3 short paragraphs: what you do, what you're looking for, how to reach you. First-person, not third. End with an invitation: "If you're hiring, mentoring, or just want to chat — happy to connect."
- **Experience.** Mirror the resume bullets but you can be slightly longer. Add media (PDFs of project decks, links to GitHub).
- **Featured.** Pin 2–3 best artifacts at the top: a project, a writeup, a talk.
- **Skills.** Endorse-able skills should match what's on your resume. Take the LinkedIn assessments for the top 3 — the badges are free signal.
- **Custom URL.** `linkedin.com/in/firstname-lastname` or `firstnamelastname`.
- **Open to Work.** Turn it on, but use the recruiter-only setting (the green badge on your photo can look desperate).

### Activity (the part most people skip)

A profile is static. Activity is what makes you findable and memorable. Honest framing first: posting publicly while job-searching feels uncomfortable for most people. You don't have to. But if you can, even a small amount of activity changes how you show up in recruiter searches and DMs.

- **Comment, don't necessarily post.** Most of the ROI is in showing up in the comments of people in your target field — substantive replies, not "Great post!" Five thoughtful comments a week makes you visible to a small but relevant audience.
- **If you do post, post 1–2x per week** while searching. Topics that work for new grads: a writeup of a project you finished, a lesson from a course or book, a specific tool you learned. Avoid generic "lessons from my journey" posts — recruiters can smell those.
- **What gets traction (rough patterns):** specific numbers and screenshots beat abstract takes; short posts beat long ones; carousels with a single insight beat link-out posts (LinkedIn currently down-ranks external links). Treat any "viral hack" advice with skepticism — the platform's algorithm changes, and chasing it isn't worth the time.
- **DM-friendliness.** Open To Work mode lets recruiters DM you directly. Set it to recruiter-only visibility. Many roles are now sourced via these DMs.

You don't need to be a "thought leader." You need to look alive — or, if posting genuinely isn't for you, focus the energy elsewhere (1:1 conversations, see doc 03).

## GitHub (if technical)

If you're applying to anything technical — engineering, data, ML, analytics — the recruiter checks your GitHub.

### What good looks like

- **Pinned repos:** 3–6 best projects. Not every assignment from class.
- **READMEs that don't suck.** Each pinned repo needs a README with: what the project does, why you built it, screenshots or demo gif, how to run it, what you learned.
- **Commit history is alive.** Empty for 12 months looks bad. Even small commits ("clean up notebook") signal activity.
- **Profile README.** A short bio at the top of your GitHub profile with links and a current focus.
- **No leaked secrets.** Search your repos for `API_KEY`, `password`, `.env`. If you've ever pushed one, rotate it and clean history.

### What kills credibility instantly

- Forks of tutorials presented as your own work.
- "Final project" repos with one giant commit titled "submit."
- A pinned repo that doesn't run and has no README.

If your GitHub is thin, **build one new project before applying.** A well-documented project beats five abandoned ones.

## Portfolio site (if applicable)

For analytics, design, product, marketing, research roles — a portfolio is differentiating. Engineering roles can usually skip it.

### Minimum viable portfolio

- A single Notion page, GitHub Pages site, or simple Squarespace.
- 3–5 case studies. Each: problem, your role, approach, result, what you'd do differently.
- Link prominently from LinkedIn and resume.
- Mobile-readable. Recruiters open links on phones.

The case studies matter more than the design. A clear Notion page beats a beautiful site with empty pages.

## Building a portfolio without "real" experience

Most new grads think a portfolio requires internship work. It doesn't. A portfolio is just evidence that you can think through a problem and ship something. Class projects, side projects, and well-framed analysis count — as long as you treat them seriously.

### When all you have is class projects

Class projects are fine. The trick is that you cannot present them the way you wrote them up for a grade. Strip the "for CS 4641 we were assigned…" framing entirely. Re-pose the project as if a real stakeholder asked the question, then walk through your work. Two specific moves:

- **Pick the 2–3 projects you can defend in depth.** Skip anything you can't explain why you chose the method. Recruiters and hiring managers will probe.
- **Add what was missing.** Most class projects stop at "we got 87% accuracy." Add the next layer yourself: a short error analysis, a comparison to a baseline, a deployment sketch, a paragraph on what you'd change. That extra mile is what makes it look like *your* work, not the assignment's.

### Platform tradeoffs (honest version)

- **Notion.** Fastest to ship. Looks fine. Downside: feels generic, every other applicant uses it, and embeds (videos, interactive plots) are clunky. Best for analytics, PM, marketing, research candidates who want to be live in a weekend.
- **GitHub Pages (Jekyll, Hugo, Astro).** Free, version-controlled, signals technical skill if you're targeting eng/data roles. Downside: takes a weekend to set up and you'll fiddle with it. Worth it if the role values that signal.
- **Substack.** Good *only* if you actually want to write regularly. Bad as a static portfolio — case studies get buried under newer posts. Pair it with one of the above; don't use it alone.
- **Squarespace / Wix / Carrd.** Cleanest for design, creative, marketing roles. Costs ~$15/mo. Recruiters in non-technical fields don't penalize you for using them.
- **Custom domain (yourname.com).** Cheap (~$12/yr) and worth it on any of the above. It's the single biggest "this person is intentional" signal.

Don't agonize. Pick one, ship in a weekend, iterate.

### Three artifacts every entry-level portfolio should include

1. **One end-to-end project case study.** A single project you took from problem statement to result, written up in depth. This is the centerpiece — see template below.
2. **One artifact that proves a specific skill.** A notebook with clean EDA, a Figma file, a SQL repo, a working deployed app. Something a recruiter can open and verify a claim from your resume in 30 seconds.
3. **A short "about" page that's a real bio, not a resume dump.** What you care about, what you're working on, what kind of role you're looking for, how to reach you. Two paragraphs is enough.

If you only have time for one of these, do #1.

### How to write a project case study

Four sections, each tight:

1. **Problem.** What was the question and why does it matter? Frame it as if a stakeholder asked it.
2. **Approach.** What you did and why — including alternatives you rejected. This is where most weak case studies skip the "why" and read like a tutorial.
3. **Result.** Concrete outcome: number, screenshot, link, decision. If the result was negative or inconclusive, say so.
4. **Reflection.** What you'd change with more time, what you learned, what surprised you. This is the section recruiters quote back to you in interviews.

Worked example (compressed):

> **Problem.** A campus food-pantry volunteer asked whether weekly demand was predictable enough to plan inventory. Stockouts had hit 3 of the last 8 weeks.
>
> **Approach.** Pulled 14 months of pantry sign-in logs (n=4,800) with permission. Tried a 7-day moving average baseline, then SARIMA, then a small gradient-boosted model with weather and academic-calendar features. Picked SARIMA — gradient boosting beat it by 4% MAE but I couldn't explain the feature importances to the volunteer team.
>
> **Result.** Forecast was within ±12% of actual demand for 9 of the next 10 weeks. The pantry shifted to a 2-week rolling order and stockouts dropped from 3-in-8 to 0-in-10 weeks. Code on GitHub, dashboard live in Streamlit.
>
> **Reflection.** I optimized for accuracy first and almost shipped a model the volunteers couldn't trust. Next time I'd ask about explainability constraints before picking the method. I'd also instrument the dashboard to log which forecasts they actually used — I have no idea if the number on the screen actually changed behavior or if they just got better at reordering.

That's ~180 words and it does more work than most 10-page class reports.

## Google yourself

Open an incognito window and search:

- Your full name.
- Your name + your school.
- Your name + the city you'll work in.

Look at the first 2 pages of results. Anything you wouldn't want a hiring manager to see (old Twitter takes, an embarrassing forum post, a tagged photo) — clean it up. Lock down personal social accounts to private. Recruiters don't grade you on a fun Instagram, but a public account full of party photos won't help.

## Email signature

While job searching, set a signature in your personal email:

```
First Last
[Target role / Grad year]
[LinkedIn URL] · [Portfolio URL]
[Phone, optional]
```

Tiny detail, real ROI. Every email becomes a conversion surface.

## What recruiters are actually looking for online

In rough order:

1. Are you a real person matching what's on the resume? (Photo, recent activity, school confirmed.)
2. Do you have anything credible beyond the resume? (Projects, writing, GitHub.)
3. Any red flags? (Crypto-pump posts, controversial public takes, ghost profile, inconsistent dates.)
4. Is there a hook to start a conversation? (A project, a shared connection, a recent post.)

Optimize the profile to hit 1, 2, and 4 within 30 seconds of landing on it.
