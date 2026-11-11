# Amazon interview stories (STAR)

Source of truth: `00-about-me/raw.md` and `01-resume-files/en.md`. Written in first person since these
are spoken interview prep, not published copy (different rule than the resume/LinkedIn files).

How to use this file: each story covers Situation / Task / Action / Result plus the extra angles
`star.md` says not to treat as exhaustive (obstacle, who else was involved, trade-offs, what you'd do
differently). Wherever raw.md doesn't give me a real answer, it's marked **[FILL IN]** instead of
invented. Don't walk into an interview with a `[FILL IN]` still blank, that's the actual content an
interviewer will dig into with follow-up questions.

Each story lists Primary LPs (lead with this story for these) and Secondary LPs (this story also
supports these if the primary story for that LP gets used elsewhere or doesn't fit the question asked).

---

## Story 1: Consolidating 32 RPA robots onto one internal SDK

**Primary:** Ownership, Invent and Simplify
**Secondary:** Think Big, Insist on the Highest Standards, Dive Deep

**Situation:** At Intelligenti Stefanini, the company runs RPA ("robot") automation for multiple
clients (bmg, inter, localiza, mercantil, necxt_bcs, omni, vivo, zurich: 32 robots total). Each robot
had been built ad hoc over time, each with its own copy of the same plumbing: web driver lifecycle,
logging, graceful shutdown, Odoo ERP connections, RabbitMQ consumer wiring. Any improvement to logging
or error handling had to be repeated robot by robot.

**Task:** Fix this without a mandate to stop and rebuild everything, since the robots still had to run
day to day for clients like Vivo (15 robots) and necxt_bcs (6 robots). I owned both the approach and the
execution.

**Action:** I designed and built an internal Python SDK centralizing the shared runtime: async job
execution, logging, telemetry, job consumer adapters, API clients (Odoo, RabbitMQ), and pipeline
control, so any robot that adopts it gets web driver lifecycle, graceful shutdown, and connection
handling built in instead of reimplemented. I proved the SDK could carry real production weight by
building the legal-operations RPA services (RabbitMQ consumption, Odoo ERP REST APIs, web scraping,
automated captcha resolution) directly on top of it before asking other robots to migrate. I'm migrating
the rest incrementally: 10 of 32 done, 22 remaining.

**Result:** 10 production robots run on the shared runtime; each one that migrates drops its own copy of
web driver/logging/shutdown/Odoo/RabbitMQ code. **[FILL IN: a concrete before/after number if you have
one, e.g. lines of code removed, incidents per robot before vs. after, or time to onboard a new robot
before vs. after the SDK existed.]**

**Trade-off:** chose incremental migration over a big-bang rewrite of 32 production robots. Slower to
reach full consistency (two patterns running side by side for a while), but doesn't destabilize
production automation that clients depend on.

**Obstacle:** **[FILL IN — not in raw.md.]** Candidates worth checking against your real memory:
convincing robot owners to migrate off something that "already works," handling a robot's in-flight
state during cutover, or a specific design problem you hit defining the SDK's abstraction boundary
(e.g., where to draw the line between "core SDK" and "robot-specific logic").

**Who else was involved:** **[FILL IN]** Solo design, or with a tech lead/manager sign-off? Did anyone
push back on the SDK approach versus just patching the worst scripts?

---

## Story 2: Observability without vendor lock-in

**Primary:** Insist on the Highest Standards, Are Right A Lot
**Secondary:** Invent and Simplify, Customer Obsession

**Situation:** Even with the new SDK, failures across a fleet of 32 RPA robots (spanning ERP
integrations, RabbitMQ, web scraping) were hard to see. There was no standard way to know a robot was
failing before a client complained.

**Task:** Make every service on the SDK observable by default, without betting the whole effort on one
vendor's proprietary agent, given how much the team's needs (and budget) could change later.

**Action:** I instrumented the full SDK runtime with OpenTelemetry end to end, an open, vendor-neutral
protocol, built Grafana dashboards for liveness and error tracking, and routed logs to Loki. Because the
instrumentation itself is OpenTelemetry and not Grafana/Loki-specific, the backend can be swapped later
(e.g. to New Relic) without touching any instrumented code.

**Result:** the team can catch failures on dashboards before they become client-facing tickets. **[FILL
IN: a number if you have one, e.g. mean time to detect/resolve an incident before vs. after, or a
specific incident the dashboards caught early.]**

**Obstacle / disconfirming belief:** **[FILL IN]** Did anyone argue for a simpler, paid observability
tool instead, and did you have to justify the OpenTelemetry investment? If yes, that's a strong real
"Are Right A Lot" (sought diverse perspectives, worked to disconfirm your own belief) and potentially a
"Have Backbone" story too, check your memory for this specifically since it would cover the biggest gap
below.

---

## Story 3: A Go TUI to find over- and under-provisioned hosts

**Primary:** Bias for Action, Frugality
**Secondary:** Ownership, Dive Deep

**Situation:** Hosts running the RPA fleet had unclear utilization: some were plausibly
over-provisioned, some were close to a CPU/memory bottleneck, and there was no fast way to tell which
was which without digging through each host manually.

**Task:** Get a fast answer to "which hosts can we shrink, and which are at risk" without waiting on a
multi-week internal tooling project.

**Action:** I built a small Terminal User Interface in Go that monitors host idleness in real time and
surfaces that directly: which hosts are idle enough to scale down, which are healthy, which are near a
CPU or memory bottleneck.

**Result:** **[FILL IN: the actual outcome, e.g. number of hosts scaled down, estimated infra cost
saved per month, or a specific bottleneck the tool caught before it caused an incident.]** Without a
number here, this story is weak on Deliver Results but still solid for Bias for Action (small fast tool
over a bigger initiative) and Frugality (right-sizing instead of just adding capacity). Worth digging up
a real number before using this one.

**Obstacle:** **[FILL IN]**

---

## Story 4: Hexagonal architecture rewrite of the e-signature integration

**Primary:** Insist on the Highest Standards, Invent and Simplify
**Secondary:** Ownership, Are Right A Lot

**Situation:** At Companhia de Estágios, the e-signature integration (a vendor dependency needed to
close contracts) had its code tightly coupled to core business-rule code. Any change to business rules
risked breaking the vendor integration and vice versa, and testing meant mocking the vendor end to end.

**Task:** Make the integration maintainable and extensible, so swapping or adding a vendor wouldn't
touch business logic, without pausing the business's use of e-signatures while doing it.

**Action:** I refactored the integration using hexagonal architecture (ports and adapters), decoupling
the business domain from the specific vendor API behind a stable interface, with vendor-specific code
isolated in an adapter. This removed the need to mock the vendor end to end for unit/integration tests
and meant a new vendor, or new vendor features, could be added without touching core business logic.

**Result:** plug-and-play vendor portability; new integrations and bug fixes became faster to ship and
tests got simpler. **[FILL IN: a number if you have one, e.g. how long a comparable integration took
before vs. after, or how many vendor-related bugs dropped after the refactor.]**

**Obstacle / possible Have Backbone angle:** **[FILL IN]** Did engineering leadership or product
initially want a quick patch instead of spending time on an architectural fix? If there was real
pushback on spending the time, that's a strong, true "Have Backbone; Disagree and Commit" story, check
this specifically, it's the other biggest open gap below.

---

## Story 5: Fixing an N+1 invoice job (1GB+ and minutes down to KB and milliseconds)

**Primary:** Dive Deep, Deliver Results
**Secondary:** Frugality, Ownership

**Situation:** A job generating the data behind client invoices took minutes to run and needed more than
1GB of memory to hold intermediate state in application code.

**Task:** Fix this, since it was a recurring operational cost in both time and memory competing for
resources with everything else on the same infrastructure.

**Action:** I dug into exactly what the job was doing instead of accepting "it's just heavy": it was
running N+1 queries, looping over records and issuing a separate query per record instead of one query
that extracts, transforms, and inserts everything needed in a single pass. I rewrote it as a single
set-based query, moving the heavy lifting into the database instead of application memory.

**Result:** memory use dropped from 1GB+ to roughly kilobytes; runtime dropped from minutes to
milliseconds. This is the clearest hard before/after metric in the whole history, use it whenever Deliver
Results or Dive Deep comes up.

**Obstacle:** recognizing the real problem was the N+1 query pattern itself, not "needs more memory" or
"needs a bigger machine," which is the easier wrong fix most people reach for first. This part is
grounded in raw.md directly (Arthur specifically called out this class of problem: heavy single queries
that should be split, versus the actual fix of moving work to the database).

**Trade-off / what I'd do differently:** **[FILL IN]** Did this require a schema change or migration?
Extra care in testing/rollout given it touches invoicing (money-sensitive data, wrong output has real
financial consequences)?

---

## Story 6: An AI recruiting agent that replaced rigid backoffice filters

**Primary:** Customer Obsession, Think Big
**Secondary:** Learn and Be Curious, Invent and Simplify

**Situation:** Recruiters at Companhia de Estágios used a backoffice system with a large, rigid set of
filter fields to search the candidate database. To find, say, marketing-internship candidates in São
Paulo, a recruiter had to know exactly which filters to combine. Worse experience than just describing
what they wanted.

**Task:** Let recruiters describe what they needed in plain language and get a usable shortlist back,
without learning the backoffice's filter taxonomy.

**Action:** I helped build an AI agent (Node.js, Next.js, OpenAI API) that takes a natural-language
request ("I need candidates for a marketing internship program in São Paulo"), interprets the actual
intent and nuance behind it, and turns that into the structured query parameters needed to search the
candidate database through a set of tools the agent could call.

**Result:** recruiters got a meaningfully better experience than the existing filter UI, able to express
nuanced requirements in plain language. **[FILL IN: adoption number, e.g. % of searches through the
agent vs. old filters, recruiter time saved per search, or direct recruiter feedback you remember.]**

**Obstacle:** **[FILL IN]** Handling ambiguous or under-specified natural-language requests? Making sure
the agent's query generation didn't miss or misinterpret candidates (a real risk with this kind of
system, worth having a specific example of catching and fixing one)?

---

## Story 7: Automating a day of manual government reporting into a 3-minute job

**Primary:** Bias for Action, Deliver Results
**Secondary:** Customer Obsession, Ownership

**Situation:** The Apprenticeship Business Unit had to extract, transform, and upload apprentice
information to a government platform for an audit process. Doing this by hand took more than a day each
time.

**Task:** Nobody asked me to fix this specifically, I noticed the business unit was burning a day or
more on a mechanical, repeatable task and decided it was worth fixing rather than "not my job."

**Action:** I gathered what the process actually needed, what data, what transformations, what the
upload target expected, then built an async job, triggerable with a single button, that runs the whole
extract/transform/upload sequence.

**Result:** what took a day or more of manual work now takes under 3 minutes end to end.

**Obstacle:** **[FILL IN]** Was the government platform's upload format/API poorly documented or
fragile? Were there edge cases in the apprentice data you had to handle?

---

## Story 8: Replacing per-client dashboard duplication with one Metabase dashboard

**Primary:** Invent and Simplify, Customer Obsession
**Secondary:** Think Big, Ownership

**Situation:** Companhia de Estágios used Google Looker Studio (free tier) to share dashboards with
clients. Every client needed their own database view and dashboard, even though they all showed the
same kind of information. A single chart change meant manually replicating it across every client's
dashboard.

**Task:** Fix the duplication while keeping each client able to see only their own data, without losing
the ability to update a chart once and have it apply everywhere.

**Action:** I implemented Metabase as a single, centralized dashboard covering all clients' data, and
generated a per-client URL with an expiring token hash that filters that one dashboard down to just that
client's information. I embedded these token URLs into the client-facing pages of the company's
systems.

**Result:** one dashboard to maintain instead of N; a chart change now applies to every client
automatically; because the token expires and is per-client, only someone who can regenerate it can
access the data, so clients only ever see their own information.

**Obstacle:** **[FILL IN]** Migrating existing clients off the old dashboards without disrupting them?
Getting the token-expiration/access-control model right the first time, given it protects client
business data?

---

## Story 9: Cutting a 3-hour financial report process to 3 minutes

**Primary:** Deliver Results, Bias for Action
**Secondary:** Learn and Be Curious, Ownership

**Situation:** At ScanSource, enterprise financial report extraction was a manual process taking about
3 hours.

**Task:** Build Python automation to replace that manual work, as part of a Product Analyst & Automation
Engineer role.

**Action:** I engineered Python automation tools for the extraction process. **[FILL IN: the specifics
that made this hard, data sources, format quirks, validation steps, raw.md only has the headline
metric, not the mechanics.]**

**Result:** processing time dropped from about 3 hours to about 3 minutes, a 98% reduction.

**Obstacle:** **[FILL IN]**

---

## Story 10: Internationalizing a CRM by talking to the people who actually used it

**Primary:** Earn Trust, Are Right A Lot
**Secondary:** Learn and Be Curious, Customer Obsession

**Situation:** ScanSource needed to internationalize a Salesforce CRM tool for a new business unit
effectively transplanted from a foreign branch, to monitor clients, providers, products, orders, and
invoices.

**Task:** Understand how the tool was actually used in its original context well enough to set it up
correctly for the new business unit, and automate parts of that process.

**Action:** I met directly with partners in the United States to understand how they used the tool, why
it was built the way it was, and how to configure it, rather than working only from documentation or
assumptions. I used that to set up the tool for the new business unit and automate parts of the
process.

**Result:** successful internationalization of the CRM for the new business unit. **[FILL IN: a concrete
outcome, e.g. how long the rollout took, or a specific gap you caught by talking to the partners
directly that documentation alone would have missed, that last one would make this a genuinely strong
"Are Right A Lot: sought diverse perspectives" story if you remember a real example.]**

**Obstacle:** **[FILL IN]** Time zone/language/communication friction? A case where what partners said
didn't match internal documentation?

---

## Principles with no grounded story (don't paper over these)

Four Leadership Principles have no real supporting material in `raw.md`, see `mapping.md` for the full
picture and specific prompts to help you find or recall a real example for each. Don't walk into an
interview assuming one of the stories above "basically" covers them, an interviewer who asks directly
about hiring, disagreement, team culture, or broad-scale responsibility will notice a stretch.
