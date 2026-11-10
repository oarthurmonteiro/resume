# Arthur Monteiro Dominguez
**Backend / Platform Engineer**
São Paulo, SP, Brazil | +55 (11) 96780-5108 | [arth.m.m@outlook.com](mailto:arth.m.m@outlook.com)
[LinkedIn](https://www.linkedin.com/in/o-arthur-monteiro/) | [GitHub](https://github.com/oarthurmonteiro)

## Summary

Backend engineer with 7+ years building the infrastructure other services run on: internal SDKs, async
job runtimes, and the observability stack underneath them. Most recently consolidated a sprawl of
ad hoc RPA scripts into one internal Python SDK, now running across 10 of 32 production robots with 22
more to migrate. Equally comfortable in backend APIs and the SQL layer below them, from query rewrites
that cut a job's memory use from gigabytes to kilobytes, to CRM/ERP integrations and distributed queues.

## Skills

- **Languages:** Python, Go, PHP, TypeScript, JavaScript, C#, Scala, SQL
- **Infra & messaging:** Docker, Kubernetes, RabbitMQ, Portainer, Linux, Nginx, Git
- **Observability:** OpenTelemetry, Grafana, Loki
- **Data:** PostgreSQL, Apache Spark, Apache Hive, Metabase
- **Frameworks:** Laravel, Zend, Next.js, .NET
- **Cloud / ERP / CRM:** Azure, GCP, Odoo, Salesforce, TOTVS Protheus

## Experience

### Sr. Automation Engineer | Intelligenti Stefanini
*May 2026 - Present*
- Architected an internal Python SDK unifying async job execution across RPA services, centralizing
  logging, telemetry, job consumer adapters, API clients, and pipeline control. 10 of 32 legacy robots
  migrated so far, each one dropping its own web driver, logging, graceful shutdown, Odoo connection,
  and RabbitMQ consumer plumbing in favor of the shared runtime.
- Built containerized RPA services for legal operations on the SDK: RabbitMQ consumption, Odoo ERP
  REST APIs, web scraping, automated captcha resolution.
- Instrumented the full SDK runtime with OpenTelemetry, built Grafana dashboards for liveness and
  error tracking, and centralized logs in Loki, on a protocol that swaps backends without touching
  instrumentation code.
- Built a Go TUI to monitor host idleness in real time, flagging which hosts can scale down and which
  are near a CPU or memory bottleneck.

### Software Engineer | Companhia de Estágios
*Sep 2021 - May 2026 (promoted from intern, Jul 2022)*
- Built an AI recruiting agent (Node.js, Next.js, OpenAI API) that turns natural-language requests
  into structured database queries, replacing a backoffice filter UI recruiters found hard to use.
- Refactored a tightly coupled e-signature integration into hexagonal architecture, decoupling
  business rules from the vendor API and simplifying both testing and future vendor swaps.
- Rewrote an invoice-data job from N+1 queries to a single extract/transform/insert query: memory use
  dropped from 1GB+ to kilobytes, runtime from minutes to milliseconds.
- Automated a government apprentice-reporting process, cutting a full day of manual work down to an
  on-demand job under 3 minutes.
- Shipped REST APIs in Laravel and legacy Zend (PHP), documented with OpenAPI, and fixed recurring
  database and code bottlenecks (missing indexes, bad joins, oversized queries) across backoffice
  systems.
- Replaced per-client dashboard duplication with one Metabase dashboard gated by expiring, per-client
  token URLs, embedded in client-facing pages.

### Backend Consultant | Freelance
*Aug 2023 - May 2024*
- Lumini: Built a Laravel bridge connecting sales and production management directly to TOTVS
  Protheus ERP.
- Intelligenti: Built a parallelized Python RPA pipeline for PDF credit contract ingestion, with
  structured log sinks for metrics analysis.

### Product Analyst & Automation Engineer | ScanSource
*Jan 2020 - Sep 2021*
- Built Python automation for enterprise financial report extraction, cutting processing time from 3
  hours to 3 minutes (98% reduction).
- Built C#/.NET applications for multi-entity financial consolidation and production validation.
- Led internationalization of a Salesforce CRM for a new business unit, working directly with
  US-based partners to map tool usage and automate parts of setup.

### Big Data Engineer | Keyrus
*Sep 2019 - Jan 2020*
- Built ETL pipelines and optimized data models across hybrid multi-cloud environments (Cloudera,
  Azure, GCP) using Scala, Python, and Apache Spark.

## Project

**Distributed Payment System** (in progress): microservices-based payment system focused on data
integrity and availability during partial failures, simulating distributed financial orchestration.
Stack: Go, C#, Docker, Kafka, PostgreSQL, TypeScript, RPC, REST.

## Education

**Bachelor's in Computer Engineering**, Universidade São Judas Tadeu (2018 - 2022)
System Design, LinuxTips (2026) · Data Analyst Nanodegree, Udacity (2022) · React Developer, IGTI
(2022) · Machine Learning Analyst Bootcamp, IGTI (2020)

## Languages

Portuguese (native) · English (fluent) · Spanish (advanced)
