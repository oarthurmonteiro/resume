# LinkedIn profile | English

## Profile structure checklist

Fill these sections, in this order of priority for a Software Engineer / Backend-Platform search:

1. Headline (keyword-dense, not just a job title)
2. About
3. Featured (pin 1-2 things: a repo, a write-up, or a slide on the SDK project if one exists)
4. Experience (6 roles, 7 position entries since Companhia de Estágios splits into two stacked
   positions under one company card, bullets below)
5. Projects (Distributed Payment System, Voice Agent, Personal Financial Management System)
6. Education
7. Licenses & certifications (all 4 courses: System Design/LinuxTips ("Descomplicando o System
   Design"), Data Analyst Nanodegree, React Developer, ML Analyst Bootcamp, listed as certifications.
   The System Design one is already on the live profile, correctly, it's a real course, not a
   mislabeled skill)
8. Skills (pin the strategic ones below so they show above the fold)
9. Languages (Portuguese, English, Spanish, with proficiency levels set)
10. Open to work (set to "Backend Engineer", "Platform Engineer", "Software Engineer", visible to
    recruiters)

## Headline (pick one)

1. Backend engineer turning fragmented automation into unified, observable infrastructure | Python, Go
2. Backend / Platform Engineer | Python, Go | Async runtimes, observability, distributed queues
3. I build the SDKs and runtimes other services run on | Python, Go, Kubernetes, OpenTelemetry

## About

I spend most of my time building the layer underneath other people's code: SDKs, job runtimes, and the
observability that tells you when they break.

At Intelligenti Stefanini I replaced a pile of ad hoc RPA scripts with a single internal Python SDK. Ten
services run on it so far, out of 32 total, 22 still to migrate. Every service that moves over stops
managing its own web driver lifecycle, logging, graceful shutdown, Odoo connections, and RabbitMQ
consumers, because the SDK already handles it. I instrumented the whole thing with OpenTelemetry and
built the Grafana dashboards the team uses to catch failures before they turn into tickets.

Before that I spent close to five years at Companhia de Estágios, moving between an AI recruiting agent
built on Node.js and the OpenAI API, a hexagonal-architecture rewrite of an e-signature integration, and
a query rewrite that took an invoice job from gigabytes of memory and minutes of runtime down to
kilobytes and milliseconds. I have also worked in big data (Spark, hybrid cloud), financial systems
(C#/.NET), and backend APIs in Laravel and PHP.

I like problems where the fix is structural, not a patch. If you are dealing with infrastructure sprawl,
flaky automation, or a backend that has outgrown its original design, message me.

## Experience bullets (for each role's Experience entry)

### Intelligenti Stefanini | Sr. Automation Engineer
- Architected a Python SDK that unified async job execution across RPA services, cutting
  per-service setup for web driver lifecycle, logging, and RabbitMQ consumers down to a shared,
  adopted-by-default runtime (10 of 32 legacy robots migrated so far, 22 remaining).
- Built containerized RPA services for legal operations on the SDK: RabbitMQ consumption, Odoo ERP
  REST APIs, web scraping, automated captcha resolution.
- Deployed OpenTelemetry end to end and shipped Grafana dashboards the team now checks before
  incidents become tickets.
- Shipped a Go TUI for real-time host-idleness monitoring, used to decide which hosts to scale down.

### Companhia de Estágios (one company card, two stacked positions, 4 yrs 9 mo combined)

LinkedIn supports multiple positions under one company entry. Use that instead of a single merged role:
it shows the promotion explicitly while still rolling up to one tenure badge on the company card.

#### Position 1: Software Engineer | Jul 2022 - May 2026 (3 yrs 11 mo)
- Shipped an AI recruiting agent (Node.js, Next.js, OpenAI API) that replaced a clunky filter UI
  with natural-language search over the candidate database.
- Redesigned an e-signature integration into hexagonal architecture, decoupling vendor APIs from
  business logic and cutting integration/testing time for future vendors.
- Rewrote an N+1-heavy invoice job into one query: memory use dropped from 1GB+ to kilobytes,
  runtime from minutes to milliseconds.
- Automated a government compliance reporting workflow, cutting a full day of manual work to under 3
  minutes.

#### Position 2: Software Engineering Intern | Sep 2021 - Jul 2022 (11 mo)
No description bullets needed, this mirrors how most intern-to-hire LinkedIn entries read. Attach the
foundational skills tags instead (e.g. JavaScript, Linux, PHP) so the entry isn't empty, without
claiming specific accomplishments that can't be dated to the internship window specifically.

### Freelance | Backend Consultant
- Lumini: Built a Laravel-to-TOTVS Protheus ERP bridge for sales and production management.
- Intelligenti: Built a parallelized Python RPA pipeline for PDF credit contract ingestion with
  structured metrics logging.

### ScanSource | Product Analyst & Automation Engineer
- Automated enterprise financial report extraction in Python, cutting a 3-hour process to 3 minutes.
- Led internationalization of a Salesforce CRM for a new business unit, partnering directly with
  US-based stakeholders.

### Keyrus | Big Data Engineer
- Built ETL pipelines and optimized data models across hybrid multi-cloud (Cloudera, Azure, GCP)
  with Scala, Python, and Apache Spark.

## Projects section

- **Distributed Payment System** (in progress): microservices payment system focused on data integrity
  and availability during partial failures. Go, C#, Docker, Kafka, PostgreSQL, TypeScript, RPC, REST.
- **Voice Agent** (in progress): real-time voice pipeline (capture, transcription, LLM, synthesis)
  built to understand how LLM voice interaction works end to end. Python, Ollama, faster-whisper,
  piper-tts.
- **Personal Financial Management System** (in progress): containerized financial platform for account
  hierarchies and transaction tracking on the BEAM VM for concurrency and fault tolerance. Elixir,
  Phoenix, Ecto, Docker, PostgreSQL.

## Top 3 skills to pin

LinkedIn only features 3 skills prominently (the "Top Skills" sidebar seen on the exported PDF), so
this list is capped at 3, not padded to 4-5 like an unordered Skills-section list could be.

1. Python
2. Docker
3. Observability / SRE

Arthur's call: lead with Python and Docker over Kubernetes, since Kubernetes isn't a skill he'd call
strong, it's in the Intelligenti Stefanini stack but not something he wants to represent as a core
competency. Pinning it anyway would risk the same overclaim problem as Kafka earlier. Python and Docker
are backed by years of real, deep use across almost every role, so they're the stronger pin.
Observability/SRE takes the third slot, backed by the OpenTelemetry/Grafana/Loki work, which is the
most senior/platform-specific signal among the real skills.

System design is a strong additive term too, backed by the SDK architecture, the hexagonal-architecture
rewrite, and now an actual course credential (LinuxTips' "Descomplicando o System Design", listed under
Certifications). It just didn't make the cut of 3 pinned slots; add it to the general Skills list in the
profile instead.

Kubernetes isn't removed from the profile, it's still accurate as a general Skills-section entry
(Intelligenti Stefanini's stack), just not one of the 3 pinned above the fold.

Apache Kafka is deliberately left off this list: it only shows up in the Distributed Payment System
project, not in any job, so pinning it as a core skill would overstate it. It stays in that project's
description, where it's already accurate, instead of in the profile-wide skill list.
