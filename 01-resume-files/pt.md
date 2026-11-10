# Arthur Monteiro Dominguez
**Engenheiro Backend / Platform**
São Paulo, SP | +55 (11) 96780-5108 | [arth.m.m@outlook.com](mailto:arth.m.m@outlook.com)
[LinkedIn](https://www.linkedin.com/in/o-arthur-monteiro/) | [GitHub](https://github.com/oarthurmonteiro)

## Resumo

Engenheiro backend com mais de 7 anos construindo a infraestrutura sobre a qual outros serviços rodam:
SDKs internos, runtimes assíncronos e a camada de observabilidade por trás deles. No cargo mais recente,
consolidou uma dispersão de scripts de RPA feitos sob demanda em um único SDK interno em Python, hoje
rodando em 10 de 32 robôs em produção, com 22 ainda a migrar. Transita com a mesma facilidade por
APIs backend e pela camada de SQL abaixo delas, de reescritas de query que reduziram o uso de memória de
um job de gigabytes para kilobytes, até integrações com CRM/ERP e filas distribuídas.

## Habilidades

- **Linguagens:** Python, Go, PHP, TypeScript, JavaScript, C#, Scala, SQL
- **Infra e mensageria:** Docker, Kubernetes, RabbitMQ, Portainer, Linux, Nginx, Git
- **Observabilidade:** OpenTelemetry, Grafana, Loki
- **Dados:** PostgreSQL, Apache Spark, Apache Hive, Metabase
- **Frameworks:** Laravel, Zend, Next.js, .NET
- **Cloud / ERP / CRM:** Azure, GCP, Odoo, Salesforce, TOTVS Protheus

## Experiência

### Sr. Automation Engineer | Intelligenti Stefanini
*Maio 2026 - Atual*
- Arquitetei um SDK interno em Python que unifica a execução assíncrona de jobs entre serviços de RPA,
  centralizando logging, telemetria, adaptadores de consumo de fila, clients de API e controle de
  pipeline. 10 de 32 robôs legados já migrados, 22 restantes, cada um deixando de gerenciar individualmente
  ciclo de vida do web driver, logging, graceful shutdown, conexão com o Odoo e consumidor do RabbitMQ.
- Construí serviços de RPA containerizados para a área jurídica em cima do SDK: consumo de RabbitMQ,
  APIs REST do Odoo ERP, web scraping e resolução automatizada de captcha.
- Instrumentei todo o runtime do SDK com OpenTelemetry, construí dashboards no Grafana para
  acompanhamento de liveness e erros, com logs centralizados no Loki, usando um protocolo aberto que
  permite trocar o backend sem alterar o código de instrumentação.
- Construí uma TUI em Go para monitorar ociosidade de hosts em tempo real, sinalizando quais podem ser
  reduzidos e quais estão perto de um gargalo de CPU ou memória.

### Software Engineer | Companhia de Estágios
*Set 2021 - Maio 2026 (promovido de estagiário em jul/2022)*
- Construí um agente de IA para recrutamento (Node.js, Next.js, API da OpenAI) que transforma pedidos
  em linguagem natural em queries estruturadas no banco, substituindo uma interface de filtros do
  backoffice difícil de usar.
- Refatorei uma integração de assinatura eletrônica fortemente acoplada para arquitetura hexagonal,
  desacoplando regras de negócio da API do fornecedor e simplificando testes e futuras trocas de
  fornecedor.
- Reescrevi um job de geração de dados de faturamento, trocando queries N+1 por uma única query de
  extração/transformação/inserção: memória caiu de mais de 1GB para kilobytes, tempo de execução de
  minutos para milissegundos.
- Automatizei um processo de envio de dados de aprendizes para plataforma do governo, reduzindo um dia
  inteiro de trabalho manual para um job sob demanda de menos de 3 minutos.
- Entreguei APIs REST em Laravel e no legado Zend (PHP), documentadas com OpenAPI, e corrigi gargalos
  recorrentes de banco e código (índices ausentes, joins mal feitos, queries grandes demais) nos
  sistemas de backoffice.
- Substituí a duplicação de dashboards por cliente por um único dashboard no Metabase, liberado por
  URLs com token expirável por cliente, embutido nas páginas voltadas ao cliente.

### Backend Consultant | Freelance
*Ago 2023 - Maio 2024*
- Lumini: construí uma ponte em Laravel conectando gestão de vendas e produção diretamente ao ERP TOTVS
  Protheus.
- Intelligenti: construí um pipeline de RPA em Python paralelizado para ingestão de contratos de
  crédito em PDF, com sinks de log estruturados para análise de métricas.

### Product Analyst & Automation Engineer | ScanSource
*Jan 2020 - Set 2021*
- Construí automações em Python para extração de relatórios financeiros corporativos, reduzindo o
  tempo de processamento de 3 horas para 3 minutos (redução de 98%).
- Construí aplicações em C#/.NET para consolidação financeira multi-entidade e validação de produção.
- Liderei a internacionalização de um CRM Salesforce para uma nova unidade de negócio, trabalhando
  diretamente com parceiros nos Estados Unidos para mapear o uso da ferramenta e automatizar parte da
  configuração.

### Big Data Engineer | Keyrus
*Set 2019 - Jan 2020*
- Construí pipelines de ETL e otimizei modelos de dados em ambientes multi-cloud híbridos (Cloudera,
  Azure, GCP) usando Scala, Python e Apache Spark.

## Projeto

**Distributed Payment System** (em construção): sistema de pagamentos baseado em microsserviços,
focado em integridade de dados e disponibilidade durante falhas parciais, simulando orquestração
financeira distribuída. Stack: Go, C#, Docker, Kafka, PostgreSQL, TypeScript, RPC, REST.

## Formação

**Bacharelado em Engenharia da Computação**, Universidade São Judas Tadeu (2018 - 2022)
System Design, LinuxTips (2026) · Data Analyst Nanodegree, Udacity (2022) · React Developer, IGTI
(2022) · Bootcamp Analista de Machine Learning, IGTI (2020)

## Idiomas

Português (nativo) · Inglês (fluente) · Espanhol (avançado)
