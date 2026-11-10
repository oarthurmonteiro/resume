# Diagnostic — resume & LinkedIn package

Honest self-assessment of `01-resume-files/` and `02-linkedin-page/`, checked against the house style
rules in `PROMPT.md` and against the real state of `github.com/oarthurmonteiro` (checked live via the
GitHub API on 2026-11-10).

## Two different scores

This diagnostic answers two different questions, and they don't move together:

1. **Deliverable quality** — did I build this well? Honest, consistent, internally grounded in your
   actual experience, free of mechanical errors. This is something I can actually assess from the files
   and your GitHub.
2. **Estimated recruiter-facing strength** — how is this likely to land with an actual recruiter or ATS?
   This is a judgment call, not a measurement. I have no data on real callback rates, no access to the
   ATS systems that will parse this, and no interviews run against it. Treat it as an informed guess,
   not a score.

## A. Deliverable quality: 92/100 (was 84, updated after the Kafka/Phoenix fix)

| Category | Score | Why |
|---|---|---|
| Narrative positioning | 90 | Single, consistent identity (Backend/Platform Engineer) across all 4 files; not generic |
| Truth-grounding | 90 | Two real violations caught and fixed (Kafka and Phoenix listed as general skills when they're project-only, see Fix #6). Worth one more independent pass since I found this myself only after you flagged the first instance |
| Metrics honesty | 90 | Real numbers used (10/32 robots, 98% reduction, 1GB→KB), nothing fabricated |
| Writing style compliance | 100 | Em dash/en dash violations fixed, see Fix #1 |
| GitHub proof backing | 65 | Real code exists and is substantial, but lives on non-default branches a recruiter won't find (see Fix #2, corrected) |
| Physical format validation | 60 | "2 pages" was estimated, never rendered and measured, see Fix #4 |

## B. Estimated recruiter-facing strength: ~71/100 (was 68, unverified estimate, not a measurement)

| Category | Score | Why |
|---|---|---|
| ATS keyword match | 85 | Kubernetes, OpenTelemetry, RabbitMQ, PostgreSQL, distributed systems all present and contextualized in real bullets, not just a tag cloud |
| Human reader impression (headline/About) | 80 | Clear hook, specific, no buzzwords; untested against an actual recruiter's attention span |
| Interview-readiness under probing | 75 | Kubernetes no longer pinned as a core skill (Arthur's call), removing that exposure. System design now backed by job architecture work plus an actual LinuxTips course, not just framing, see Fix #5/#7/#8 |
| Portfolio click-through experience | 55 | A recruiter who clicks the GitHub link today sees an empty repo (`voice-agent-restaurant`) and a repo with no visible connection to "finance" (`miau`), see Fix #2 |
| Social proof (recommendations, endorsements) | 30 | Essentially absent right now, see Fix #3 |

---

## Fix #1 — Em dash / en dash violation — DONE

`PROMPT.md`'s house style explicitly bans `—` and `–` ("use commas, periods, or `|` instead"). All 5
generated files broke this rule (56 occurrences total, mostly `Title — Company` separators and
`May 2026 – Present` date ranges). Fixed: `—` as a title/company separator became `|`, `—` introducing
a description became `:`, en-dash date ranges became plain ASCII hyphens. Verified zero `—`/`–`
remaining in `00-about-me/experiences.md`, `01-resume-files/*.md`, `02-linkedin-page/*.md`.

## Fix #2 — GitHub discoverability (corrected after Arthur's input)

My first pass checked only each repo's default (`main`) branch and concluded the work didn't exist.
That was wrong. Checked branches directly:

- **`voice-agent-restaurant`**: `main` is genuinely empty (just `.gitignore` + a 1-line README). The
  real implementation, with a proper README, `docs/DESIGN.md`, `docs/PROJECT.md`, and the full
  `src/restaurant_voice_agent/` package, lives on the **`synchronous-flow`** branch.
- **`miau`**: `main` has the real Phoenix/Elixir app (`app/lib/app/credit/`, `app/lib/app/ledger/`,
  `app/lib/app/portfolio/account.ex`, `balance_history.ex`), which matches "Personal Financial
  Management System" exactly, account hierarchies, credit, ledger, transactions. The **top-level
  `README.md` on `main`** is still just 11 lines in Portuguese ("In development") and doesn't describe
  any of that. A `trying_things` branch exists too but has even less.

Revised finding: **the code backs the resume's claims.** The actual gap is discoverability, not
substance:
1. GitHub shows visitors the default branch. For `voice-agent-restaurant`, that's the empty one, so
   a recruiter who clicks through sees nothing. Recommend making `synchronous-flow` the default branch
   (or merging it into `main`) before the GitHub link goes out on a resume.
2. `miau`'s `main` branch has the right code but the README doesn't say what the app does. A 5-minute
   rewrite of that README (English, describing accounts/ledger/credit/portfolio) would close this gap
   entirely, no code changes needed.
3. `payment-system`'s README is solid (architecture, stack, setup) but has a typo ("phisical") and
   mixes English prose with Portuguese shell comments. Minor polish, not a rewrite.
4. Still true: no profile README (`oarthurmonteiro/oarthurmonteiro` repo doesn't exist), so there's no
   "here's who I am" landing page above the repo grid.

This is a 1-2 hour fix, not a "go build the project" fix: the engineering work is already done.

## Fix #3 — LinkedIn social proof isn't addressed at all

`02-linkedin-page/*.md` covers headline, About, experience bullets, skills, and structure order, but
says nothing about:
- **Recommendations.** Platinum-tier LinkedIn profiles (per the audit in `PROMPT.md`) lean heavily on 2-3
  written recommendations from managers/peers. None exist yet, and no generated file asks for them.
- **"Open to work" visibility settings** (public vs. recruiters-only) and target job titles — mentioned
  in the checklist but not decided.
- **Skill endorsements** — LinkedIn's algorithm weights skills with 10+ endorsements higher in recruiter
  search; a brand-new skill list (Kubernetes, Kafka, etc.) starts at zero.

None of this is something I can write for you; it needs action from people who worked with you. Worth a
follow-up round once the profile is live.

## Fix #4 — "2 pages" was never actually measured

The resume files were written to a word-count estimate, not rendered and checked. Before calling the
resume final: export `01-resume-files/en.md` and `pt.md` to PDF (or paste into the template you'll
actually use) and confirm each is ≤2 pages at a normal font size. If either runs long, the Freelance and
Keyrus entries are the safest to compress first (already the thinnest content).

## Fix #5 — Certification/skill mismatch (partially resolved)

Originally: Kubernetes and System Design were pushed as strategic skills to pin on LinkedIn, but neither
had a certification behind it.

- **Kubernetes**: resolved differently than expected. Arthur judged it's not actually a strong skill for
  him and chose not to pin it at all (see Fix #8), leading with Python/Docker instead. No cert needed
  since it's no longer being represented as a core competency.
- **System Design**: turns out this one does have a certification, see Fix #7. The LinuxTips course
  listed in `raw.md` as "Design System" is actually "Descomplicando o System Design," a real course on
  the exact skill being pinned. This resolves the original concern; System design is now backed by job
  architecture work (SDK, hexagonal-architecture refactor) *and* a named course.

## Fix #7 — Course name was wrong everywhere: "Design System" → "System Design" — DONE

`raw.md` listed a LinuxTips course as "**Design System**: LinuxTips | Apr 2026." I took that at face
value and assumed it meant a UI/design-system course (component libraries, tokens, that kind of thing).
Arthur corrected it: the real course is "Descomplicando o System Design," about software system design,
not UI design systems. The mislabel originated in `raw.md`, not something I introduced, but I propagated
it without questioning it, and then actively told Arthur his LinkedIn had a mix-up (System Design listed
as a certification) when his profile was actually correct and my assumption was wrong.

Fixed: `raw.md`, `00-about-me/experiences.md`, `01-resume-files/en.md`, `01-resume-files/pt.md`,
`02-linkedin-page/en.md`, `02-linkedin-page/pt.md`, all now say "System Design" (with the full course
title noted where useful). Also corrected the "Top skills to pin" rationale and this diagnostic's
Fix #5, since "System design has no cert behind it" is no longer true.

## Fix #8 — Kubernetes deprioritized from pinned skills (Arthur's call) — DONE

Arthur judged Kubernetes isn't a skill he'd call strong, despite being in the Intelligenti Stefanini
stack, and didn't want it represented as a core competency. Swapped it out of the "Top skills to pin"
list in `02-linkedin-page/en.md` and `pt.md` for Python and Docker, which have deep, real, cross-role
backing. The list is also now explicitly capped at 3 (matching LinkedIn's actual "Top Skills" sidebar,
confirmed from the exported PDF), not 4-5 like a general Skills list could hold. Kubernetes stays in the
general Skills section, just isn't one of the 3 pinned above the fold.

## Fix #6 — Kafka and Phoenix listed as general skills, not job-grounded — DONE

You flagged this directly: Kafka and Phoenix were in the "top skills to pin" (LinkedIn) and in the
general Skills section (resume), as if they were production skills. Checked against every job's stack
in `raw.md`: neither appears in any job, only in personal projects (Kafka in Distributed Payment System,
Phoenix/Ecto in Personal Financial Management System). This is exactly the kind of "manufactured
significance" `PROMPT.md`'s truth-integrity rule bans, and I introduced it myself without being asked.

Fixed:
- `02-linkedin-page/en.md` and `pt.md`: removed Kafka from the strategic-skills list, replaced the "top
  5" framing with an unnumbered list of 4, added a line explaining why Kafka stays in the project
  description instead.
- `01-resume-files/en.md` and `pt.md`: removed Kafka from "Infra & messaging" and Phoenix from
  "Frameworks" in the Skills section. Kafka still correctly appears under the Project section (it's
  honest there). Phoenix doesn't appear anywhere else on the resume since the Elixir project isn't on
  it, so it's gone entirely.
- `00-about-me/experiences.md`: kept both in the full skill inventory (it's the working reference, not
  public copy) but annotated that they're project-only, not job-grounded.

Worth noting: I didn't catch this on my own first pass. The diagnostic that found the em dash and
GitHub issues didn't check skill-to-job grounding at all, which is the same category of problem as the
banned-vocabulary and no-em-dash checks. Treat the 90/100 "Truth-grounding" score above as "fixed once
found," not "verified clean," since a second read-through specifically for this pattern hasn't happened.

---

## What's left

For **deliverable quality** (A, currently 92):
1. ~~Fix the em dash/en dash violations.~~ Done.
2. ~~Remove Kafka/Phoenix from general skill lists where they're not job-grounded.~~ Done.
3. Make `synchronous-flow` the default branch on `voice-agent-restaurant` (or merge to `main`), rewrite
   `miau`'s top-level README to describe the financial platform, polish `payment-system`'s typo/language
   mix, add a short profile README (1-2 hours total).
4. Render both resume files to PDF and confirm the 2-page limit holds (10 min).
5. One more read-through specifically hunting for other skill-to-job mismatches, since this category
   wasn't checked until you caught the first instance.

For **estimated recruiter-facing strength** (B, currently ~71, unverified): mostly outside what this
session can do directly.
1. Decide "Open to work" visibility and target titles.
2. Collect 2-3 LinkedIn recommendations from former managers/peers.
3. Fix items 3-4 above (GitHub discoverability directly raises the portfolio click-through score).
4. ~~Resolve the Kubernetes/System Design certification gap.~~ Done differently than planned: Kubernetes
   deprioritized rather than certified (Fix #8), System Design turned out to already have a real course
   behind it (Fix #7). Be ready to go deep on the Distributed Payment System project under interview
   questioning regardless, since it's still the main hands-on proof of the Go/Kafka/distributed-systems
   claims.

The deliverable itself is close to done. What's left on the recruiter-facing side is mostly proof and
social signal that only you, and the people who worked with you, can supply.
