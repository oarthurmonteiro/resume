# Airbnb virtual onsite: prep plan

Based on the two candidate-prep PDFs in this folder and `00-about-me/raw.md`. Five interviews total:
Core Values (45 min, non-technical) + four technical ones via CodeSignal (General Coding, Code Review,
Architecture/System Design, Technical Experience).

## 1. Core Values interview (45 min)

Not vetted on technical skill, explicitly says so. Graded on fit with Airbnb's four values. Personal-life
examples are explicitly welcome, not just career ones.

| Core value | What it means | Best grounded story from raw.md |
|---|---|---|
| Champion the Mission | united with your community, creates connection/belonging | The pattern across ScanSource and Companhia de Estágios: noticing people losing hours or days to manual, repetitive data-moving work, and automating it (see below) |
| Be a Host | caring, open, encouraging to everyone you work with | The Laravel/Zend feature work: raw.md specifically describes talking directly to "stakeholders, clients, users and anyone that participates of the process to understand the user pain" before building anything |
| Be a Cereal Entrepreneur | determined and creative, turns bold ambitions into reality | The SDK consolidation at Intelligenti Stefanini: turned 32 ad hoc, undocumented robot scripts into one coherent system, on your own initiative, mid-flight, without stopping the business |
| Embrace the Adventure | curiosity, optimism, belief people can grow | The personal projects (Voice Agent, Elixir/Phoenix financial system) plus picking up Go for the TUI tool and OpenTelemetry/observability on the job: real pattern of learning unfamiliar stacks by choice |

**Champion the Mission, expanded (your framing, this is the strongest one in the table):** at both
ScanSource (financial report extraction) and Companhia de Estágios (government apprentice reporting),
the actual work people were doing was the same shape: log into a system, collect information, apply
whatever transformation was needed, load it somewhere else, a manual, informal ETL. They were losing
hours (ScanSource: ~3 hours a run) or full days (Companhia de Estágios: a day or more) to this, work that
didn't need a human doing it by hand. Nobody asked you to fix either one. You noticed, went and talked
directly to the people doing the manual work to understand why it hadn't already been automated, and
only then built the automation, freeing their time for the Apprenticeship Business Unit and the
financial team respectively. The connection-and-belonging angle isn't the automation itself, it's that
you got there by talking to the people first, not by assuming you already knew the problem.

Metabase (one dashboard instead of fragmented per-client ones) is a reasonable backup for this value if
asked for a second example, but lean on the automation pattern first, it's more clearly about people, not
just architecture.

**Gap, be honest about this:** the sample questions they gave ("most difficult decision you've had to
make," "something important that didn't go as planned, what did you do") are deliberately personal and
reflective, not project-recap questions. Nothing in `raw.md` answers these directly since it's a
professional-accomplishments document. This needs real reflection from you, not something I can
source-check. Spend time on these two specifically before the interview, ideally with a genuine
personal-life example for at least one of them, since the doc explicitly invites that.

## 2. General Coding Interview (45 min, CodeSignal)

Generalist algorithmic question, Big-O, data structures. Graded on Technical Quality, Work Execution,
Communication (talk through your approach, don't just silently code).

**Honest gap:** `raw.md` has no algorithm-interview-style material, it's a record of applied engineering
work, not LeetCode practice. This interview isn't really "based in raw.md," it's a separate skill to
train directly:
- Refresh arrays/strings/hash maps/trees/graphs, and the common technique families (two pointers,
  sliding window, BFS/DFS, DP basics).
- Practice narrating your approach out loud before coding, this is explicitly part of the Communication
  competency being graded, not just whether the code runs.
- Use CodeSignal's own practice environment first so the tooling itself isn't a surprise.

## 3. Code Review Interview (45 min, CodeSignal, screen-share required)

Review intentionally-flawed Change Requests for performance, concurrency, observability, readability,
testability. Graded on finding real faults (quantity and quality both matter) and clearly defending your
reasoning out loud.

**This one is grounded.** `raw.md` describes this exact muscle already in production use at Companhia de
Estágios: "database bottlenecks (queries not using the right index, bad comparisons, joins not helping
filters/selects, bad aggregations), code bottlenecks (a single heavy query that should be split into
lighter ones, expensive file I/O)." That's close to a literal description of what this interview is
testing.

What to actually practice: not the pattern recognition (you clearly have it), but **narrating it out
loud while screen-sharing**, in real time, to someone watching. That's a different skill than fixing it
quietly and shipping a PR. Do at least one timed mock where you talk through found issues as you find
them, not after.

## 4. Architecture / System Design Interview (60 min, CodeSignal)

Given a module/feature, produce a system architecture. Interview tips from the doc: ask lots of
questions, start high-level before component details, talk through trade-offs and justify technology
choices, take design feedback well.

**Grounded strengths to lean on:**
- The N+1 invoice-job fix (`raw.md`): direct, concrete evidence of understanding when to push work into
  the database vs. application code, exactly the kind of trade-off this interview wants narrated.
- The hexagonal-architecture e-signature refactor: evidence of deliberately designing a seam (port/adapter)
  to isolate a volatile dependency, a real example of "component-level" design thinking past the obvious
  solution.
- The SDK project: real multi-service architecture experience (async job runtime, pluggable adapters for
  Odoo/RabbitMQ), directly relevant if the given prompt is anything infra/platform-shaped.

**Prep gap:** the doc specifically calls out database indexing, relational vs. key/value modeling, and
server performance setup as technologies to be familiar with. Your real experience is Postgres-heavy and
query-optimization-heavy (strong), but if the prompt leans toward KV/NoSQL modeling or horizontal scaling
patterns you haven't touched in `raw.md` (sharding, replication topologies, caching layers), that's worth
a quick refresh beforehand, it's not covered by your work history as documented.

## 5. Technical Experience Interview (60 min, CodeSignal)

A deep-dive on one past project: impact/scope, technical judgement, collaboration/conflict, leading
through ambiguity, balancing present vs. future, communication. Starts with a quick resume overview, then
goes deep on one thing.

**Recommendation changed: lead with the hexagonal architecture refactor instead of the SDK project.**
The conflict gap flagged below is now resolved, and resolved specifically on this project, which makes
it the more complete single story: it now covers every competency in the rubric without needing a second
project stitched in for conflict.

- **Impact & Scope:** mission-critical e-signature integration, used to close contracts, not a side
  system.
- **Technical Judgement & Decision Making:** choosing ports/adapters specifically to decouple business
  rules from a volatile third-party dependency, a deliberate architectural call, not the default.
- **Collaboration & Navigating Conflict (now grounded):** the PO wanted to keep the code as-is, planning
  to negotiate pricing with the current vendor instead, and judged the refactor's upfront dev cost as
  higher than just keeping things coupled. You argued the PO's framing only priced the immediate cost,
  not the compounding one: more features would land on the coupled code before any forced vendor change,
  making a later, forced migration (price hike, vendor failure) far more expensive than paying the
  decoupling cost now. You pushed back, the PO agreed, you proceeded with the refactor.
- **Balancing Present & Future:** this is the same disagreement, essentially a cost-timing argument
  (cheaper now vs. cheaper later), the cleanest possible example of this competency.
- **Communication:** you have a concrete after-the-fact signal here too, other developers' comments and
  feedback that introducing new features became easier post-refactor, not just your own account of it.

**The SDK consolidation is still a strong backup**, particularly if asked for a second project or if the
interviewer wants to go bigger on scope (32 robots across 8 clients vs. one integration). Its own
Collaboration & Navigating Conflict gap is still open, don't reach for it as primary unless you've since
recalled or prepared a real conflict example from that project too.

**Also worth remembering going in:** per the doc's NDA note, stick to what's publicly describable, no
proprietary specifics about either employer's clients or internals beyond what you'd already say on a
resume.

---

## What to actually do before the interview

1. Write out real answers to the two Core Values sample questions, from genuine reflection, not from
   this document.
2. ~~Pick your real Collaboration & Navigating Conflict example for the Technical Experience
   interview.~~ Done: the PO disagreement on the hexagonal architecture refactor. Rehearse narrating it
   with the cost-timing argument front and center, that's the actual judgment call being graded.
3. Do algorithm practice for the General Coding interview, this is the one interview truly outside what
   `raw.md` can prepare you for.
4. Run one timed, out-loud mock of the Code Review interview, you already have the technical instinct,
   the gap is narrating it live.
5. Skim the System Design doc's linked resources on indexing and relational-vs-KV modeling if your
   target domain might lean non-relational.
