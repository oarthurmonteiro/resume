# Structured profile: source of truth

Positioning: **Backend / Platform Engineer** (not generic "Software Engineer"). Leads with internal
tooling/SDKs, async runtimes, observability, distributed messaging. Backend web work (Laravel/Next.js)
and data-layer optimization support the story but aren't the headline.

Target market: Brazil and remote/international, equally. EN and PT versions are each written to stand
alone, not translated line by line.

Metrics policy: only use numbers Arthur confirmed. Where he didn't have a number (e.g. maintenance time
reduction), the bullet stays qualitative and names the concrete things that got centralized instead of
inventing a percentage.

Decision log:
- Personal projects on the 2-page resume: **Distributed Payment System only** (Go/Kafka/Postgres,
  matches Backend/Platform identity). Voice Agent and the Elixir financial system go on LinkedIn only.
- The IDC Latin America research internship (Mar 2018-Aug 2019, phone research, not technical) found in
  a prior LinkedIn audit is **not** in raw.md and is **omitted** from both resume and LinkedIn rewrite.
  It predates Keyrus, is non-technical, and competes for space with stronger, more recent material. Flag
  to Arthur if he wants it added back.
- Companhia de Estágios: raw.md gives one continuous role (Sep 2021-May 2026). A prior audit shows he
  was promoted from Estagiário to Software Engineer in Jul 2022. Keeping it as one entry but noting the
  promotion inline for credibility.

---

## Intelligenti Stefanini | Sr. Automation Engineer (May 2026 - Present)

Confirmed by Arthur: exact robot inventory is bmg (2), inter (1), localiza (1), mercantil (1),
necxt_bcs (6), omni (2), vivo (15), zurich (4): 32 robots total, 10 migrated onto the new SDK so far,
22 remaining. No confirmed % reduction in maintenance time yet (robots still need per-service timeout
tuning), but the SDK has already removed the need to handle, per service: web driver lifecycle, logging,
graceful shutdown, Odoo connections, RabbitMQ consumers, and other runtime plumbing.

- Architected an internal Python SDK unifying async job execution across RPA services; centralizes
  logging, telemetry, job consumer adapters, API clients, and pipeline control. 10 of 32 legacy robots
  migrated so far, 22 remaining.
- Built containerized RPA services for legal operations on the SDK: RabbitMQ consumption, Odoo ERP REST
  APIs, web scraping, automated captcha resolution.
- Instrumented the full SDK runtime with OpenTelemetry; built Grafana dashboards for liveness/error
  tracking, logs centralized in Loki. Chose an open protocol specifically so the backend (Grafana/Loki)
  can be swapped (e.g. to New Relic) without touching instrumentation code.
- Built a Go TUI to monitor host idleness in real time: which hosts can scale down, which are near a
  CPU/memory bottleneck, which are healthy.

## Companhia de Estágios | Software Engineer (Sep 2021 - May 2026, promoted from intern Jul 2022)

- Built an AI recruiting agent (Node.js, Next.js, OpenAI API) that takes natural-language requests
  ("marketing internship candidates in São Paulo") and turns them into structured database queries,
  replacing a clunky backoffice filter UI.
- Refactored a tightly coupled e-signature integration into hexagonal architecture, decoupling business
  rules from the vendor API; simplified unit/integration testing and made new vendor integrations
  plug-and-play.
- Rewrote the invoice-data generation job: replaced N+1 queries with a single extract/transform/insert
  query. Memory dropped from 1GB+ to kilobytes, runtime from minutes to milliseconds.
- Automated government apprentice reporting (data extraction + upload for audit); previously a full day
  of manual work, now an on-demand async job under 3 minutes.
- Shipped REST APIs and features in Laravel and legacy Zend (PHP), documented with OpenAPI; worked
  directly with stakeholders to turn pain points into trackable, measurable user stories.
- Diagnosed and fixed recurring DB/code bottlenecks: missing indexes, bad joins/aggregations, oversized
  single queries that should've been split, expensive file I/O.
- Replaced per-client dashboard duplication (Google Looker Studio) with one Metabase dashboard gated by
  expiring per-client token URLs, embedded in client-facing pages.

## Freelance | Backend Consultant (Aug 2023 - May 2024)

- Lumini (May 2024): Laravel bridge connecting sales/production management directly to TOTVS Protheus
  ERP.
- Intelligenti (Aug 2023): parallelized Python RPA pipeline for PDF credit contract ingestion, with
  structured log sinks for metrics analysis.

## ScanSource | Product Analyst & Automation Engineer (Jan 2020 - Sep 2021)

- Python automation for enterprise financial report extraction: 3 hours → 3 minutes (98% reduction).
- C#/.NET applications for multi-entity financial consolidation and production validation.
- Led internationalization of a Salesforce CRM for a new business unit transplanted from a foreign
  branch; worked directly with US-based partners to map tool usage/configuration, automated parts of
  setup.

## Keyrus | Big Data Engineer (Sep 2019 - Jan 2020)

- Built ETL pipelines, optimized data models across hybrid multi-cloud (Cloudera, Azure, GCP) using
  Scala, Python, Apache Spark.

---

## Skills, grouped

- **Languages:** Python, Go, PHP, TypeScript, JavaScript, C#, Scala, SQL
- **Infra & messaging:** Docker, Kubernetes, Portainer, RabbitMQ, Linux, Nginx, Git, Shell
  (Kafka omitted here: project-only, not from a job; see Personal projects below)
- **Observability:** OpenTelemetry, Grafana, Loki
- **Data:** PostgreSQL, Apache Spark, Apache Hive, Metabase
- **Frameworks:** Laravel, Zend, Next.js, .NET
  (Phoenix, Ecto omitted here: project-only, not from a job; see Personal projects below)
- **Cloud/ERP/CRM:** Azure, GCP, Odoo, Salesforce, TOTVS Protheus

## Education

- Bachelor's in Computer Engineering, Universidade São Judas Tadeu (Jan 2018 - Dec 2022)
- System Design (course: "Descomplicando o System Design"), LinuxTips (Apr 2026)
- Data Analyst Nanodegree, Udacity (Nov 2022)
- React Developer, IGTI (Jun 2022)
- Machine Learning Analyst Bootcamp, IGTI (Sep 2020)

## Languages

Portuguese (native), English (fluent), Spanish (advanced)

## Personal projects

- **Distributed Payment System** (In Building): Go, C#, Docker, Kafka, PostgreSQL, TypeScript, RPC,
  REST. On resume.
- **Voice Agent** (In Building): Python, Ollama, faster-whisper, piper-tts. LinkedIn only.
- **Personal Financial Management System** (In Building): Elixir, Phoenix, Ecto, Docker, PostgreSQL.
  LinkedIn only.
