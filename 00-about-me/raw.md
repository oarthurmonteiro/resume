# Arthur Monteiro Dominguez
**Software Engineer**  
São Paulo, SP | +55 (11) 96780-5108 | [arth.m.m@outlook.com](mailto:arth.m.m@outlook.com)  
[LinkedIn](https://www.linkedin.com/in/o-arthur-monteiro/) | [GitHub](https://github.com/oarthurmonteiro)


## Experiences

### Sr. Automation Engineer
**Intelligenti Stefanini** | *May 2026 - Present*

* Architected and deployed a standardized internal Python SDK to replace legacy ad-hoc bot scripts from RPA services unifing async job runtime from 10+ services reducing maintenance and code repetition since most of the things were centralized in the SDK like logging, telemetry, job consumer adapters, api clients, pipeline control and others.
* Developed RPA containerized services for legal operations integrating RabbitMQ consuming, Odoo ERP REST APIs, web scraping and automated captcha resolution within the core SDK framework to reduce process mean time to resolution and improve scalability.
* Implemented end-to-end OpenTelemetry integration across all SDK runtime nodes, building interactive Grafana dashboards for liveness tracking and error analysis, collecting logs into Loki allowing debugging and investigation easier to track through all the job pipeline and using a open protocol that is more flexible to swap final providers like Grafana to NewRelic, for example.
* Built a TUI (Terminal User Interface) using Go to monitor and analyse hosts idleness to help diagnose which ones were enable to be rescaled down and which ones were operating in a ok capacity. Which ones were possible bottlenecks of memory or CPU and which ones were ok.

#### Stacks 
* Python
* Docker
* RabbitMQ
* Odoo
* Portainer
* Kubernetes
* Go
* Git
* OpenTelemetry
* Grafana
* Linux

### Software Engineer
**Companhia de Estágios** | *Sep 2021 - May 2026*
* Helped to develop a chat Agent AI to help recruiters to find candidates in our database using natural language. The Agent received a instruction like "I need candidates to a marketing internship program in São Paulo" and the agent consumed tools able to query and filter this information easier and return a shortlist for the recruiters. This was a better User Experince than our BackOffice system and their variaty of filter slots. The agent could understand better a nuance of some requirement and transform this into the parameters necessary to query. This agent was built in Node.js using Next.JS framewok and OpenAI APIs.
* Reestructured using Hexagonal Architecture an e-signature integration that was to coupled with core business rules code. Decoupled business domains from third-party vendor APIs for plug-and-play portability making easier new extensions, consuming new features and fixing bugs, beyond simplifyed testing (unit and integration).
* Improved job responsible to generate the data used for create the invoices. Previously my changes, the job took minutes and was necessary more than 1GB of memory to store everything that was made in code. The problem was that the code was doing N+1 queries that could be resolved to a single query that extract everything needed, transform what necessary and insert into a different table. The result was memory consumption reduced to almost kbs (since the heavier part was now into database) and time to miliseconds.
* Created an RPA responsible to query apprentices information and upload to .gov platform due audit process. This RPA was created after checking the Apprenticeship Business Unit needed to take more than one day to extract, transform and upload this information. This cost time that could be used for other things, than I collected what was needed to automate the process and then created an async job that was dispatched through a button and consumed 3 minutes or less to do what took a day or more.
* Implemented new features in Laravel and Zend Legacy Framework (PHP) for ours backoffice systems. Developed REST APIs, and documentted using OpenAPI. The process for this was talk with stakeholdes, clients, users and anyone that participates of the process to understand the user pain and create a user history that would be used to split into tasks. Each task could be tracked and metrified with stakeholders to understand if the implementaion was having a positive impact and if really solved the problem.
* Investigated and solved many bugs as database bottlenacks (like queries that was not using a right index, making bad comparations, joins that was not helping in filters or selects, bad aggregations, and others), code bottlenacks (like trying to make a single heavy query when the process could be split into multiple lighter queries and make the code easier to follow and understand what was happening there, or trying to read/write expensive files causing I/O problems) and third-party integrations.
* Implemented Metabase as a dashboard centralizer to solve the problem of client dashboards replication. Before this we used Google Look Studio tool but as a free service, for every client was necessary create a new database view and a new dashboard to share to the client. This was problematic because a single change in a chart, was necessary to replicate to every other dashboard since every client should be able to see the same kind of informations. To solve this, I implemented the Metabase dashboard where was created a single dashboard that show all information, but for every client was shared a single url with a token hash that filter the dash with only their infos. The token has time expiration and in this way solved a problem of only who could regenerate the token could have access to the data and the clients could only view their only information. This dashs was embbed in our client-only pages in our systems.

#### Stacks
* PHP
* Docker
* Laravel
* Zend
* PostgreSQL
* SQL
* Nginx
* Linux
* JavaScript
* TypeScript
* Next.JS
* RabbitMQ
* Cloud
* Shell

### Backend Consultant
**Freelance** 
* **Lumini (May/2024):** Engineered a Laravel-based sales and production management bridge integrated directly with TOTVS Protheus ERP.
* **Intelligenti (Aug/2023):** Build a parallelized Python RPA pipeline for PDF credit contract ingestion, complete with structured log sinks for metrics analysis.

#### Stacks
* Python
* PHP
* Laravel

### Product Analyst & Automation Engineer
**ScanSource** | *Jan 2020 - Sep 2021*
* Engineered Python automation tools for enterprise financial report extraction, reducing data processing cycle times by 98% (from 3 hours to 3 minutes).
* Developed C#/.NET applications for multi-entity financial consolidation and production validation pipelines.
* Headed a internalization of a CRM Salesforce tool for a new Business Unit from a foreign branch to monitor clients, providers, products, orders and invoices. I needed to meet various partners from united states to understand how they used the tool, for what the tool was developed, how to set things and automated some process.

#### Stacks
* Python
* C#
* .NET
* Javascript
* Salesforce

### Big Data Engineer
**Keyrus** | *Sep 2019 - Jan 2020*
* Built scalable ETL data pipelines and optimized data models across hybrid multi-cloud environments using Scala, Python and Apache Spark.

#### Stack
* Python
* Scala
* Apache Spark
* Cloudera
* Horton
* Azure
* GCP
* SQL
* Apache Hive


## Education

### Graduation
* **Bachelor's in Computer Engineering:** Universidade São Judas Tadeu | *Jan 2018 - Dec 2022*

### Courses
* **System Design** (Descomplicando o System Design): LinuxTips | *Apr 2026*
* **Data Analyst Nanodegree**: Udacity | *Nov 2022*
* **React Developer:** Instituto de Gestão e Tecnologia da Informação | *Jun 2022*
* **Machine Learning Analyst Bootcamp:** Instituto de Gestão e Tecnologia da Informação | *Sep 2020*

### Languages
* **Portuguese:** Native
* **English:** Fluent
* **Spanish:** Advanced


## Personal Projects

### Voice Agent - *In Building*
An AI Voice Agent built to understand about LLMs. Using python and some built-in tools developed a stream pipeline to capture audio, transcript into text, load into some LLM, and back the sentences in audio. Currently the flow is synchronous being necessary to have some external input to start the audio capture and await for all the llm response before continuous. The intention is to have a Voice Audio Detector to stop llm for some process when user interrupt and start to talk having a natural and realtime experience of chat with someone. 

#### Stack
* Python
* Ollama
* faster-whisper
* piper-tts

### Distributed Payment System - *In Building*
A high-resilience, microservices-based payment ecosystem designed to maintain data integrity and availability during partial system failures. The project focuses on simulating real-world financial orchestration and distributed state management. 

#### Stack
* Go
* C#
* Docker
* Kafka
* PostgreSQL
* TypeScript
* RPC
* REST API

### Personal Financial Management System - *In Building*
Developed a containerized financial platform focused on tracking account hierarchies and transaction metadata. The project leveraged the BEAM VM to ensure a highly concurrent and fault-tolerant environment for real-time data processing.

#### Stack
* Elixir
* Phoenix
* Ecto
* Docker
* PostgreSQL
