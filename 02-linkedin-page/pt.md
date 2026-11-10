# Perfil do LinkedIn | Português

## Checklist de estrutura do perfil

Preencher nesta ordem de prioridade para buscas de Engenheiro de Software / Backend-Platform:

1. Headline (denso em palavras-chave, não só o cargo)
2. Sobre
3. Destaques (fixar 1-2 itens: um repositório, um artigo ou um material sobre o projeto do SDK, se
   existir)
4. Experiência (6 cargos, 7 entradas de posição já que Companhia de Estágios se divide em dois cargos
   empilhados sob um único card de empresa, bullets abaixo)
5. Projetos (Distributed Payment System, Voice Agent, Personal Financial Management System)
6. Formação acadêmica
7. Licenças e certificados (os 4 cursos: System Design/LinuxTips ("Descomplicando o System Design"),
   Data Analyst Nanodegree, React Developer, Bootcamp Analista de Machine Learning, cadastrados como
   certificações. O curso de System Design já está no perfil atual, corretamente, é um curso real, não
   uma competência mal rotulada)
8. Competências (fixar as estratégicas do final deste documento para aparecerem no topo)
9. Idiomas (português, inglês, espanhol, com nível de proficiência definido)
10. Aberto a oportunidades: marcar "Engenheiro Backend", "Platform Engineer", "Engenheiro de Software",
    visível para recrutadores

## Headline (escolher uma)

1. Engenheiro backend que transforma automação fragmentada em infraestrutura unificada e observável |
   Python, Go
2. Engenheiro Backend / Platform | Python, Go | Runtimes assíncronos, observabilidade, filas
   distribuídas
3. Construo os SDKs e runtimes sobre os quais outros serviços rodam | Python, Go, Kubernetes,
   OpenTelemetry

## Sobre

Passo a maior parte do meu tempo construindo a camada que fica embaixo do código de outras pessoas:
SDKs, runtimes de jobs e a observabilidade que avisa quando algo quebra.

Na Intelligenti Stefanini, substituí uma pilha de scripts de RPA feitos sob demanda por um único SDK
interno em Python. Hoje 10 dos 32 robôs rodam nele, e ainda há 22 para migrar. Cada serviço que
migra deixa de gerenciar sozinho ciclo de vida do web driver, logging, graceful shutdown, conexão com o
Odoo e consumidor do RabbitMQ, porque o SDK já resolve isso. Instrumentei tudo com OpenTelemetry e
construí os dashboards no Grafana que o time usa para pegar falhas antes que virem chamado.

Antes disso, passei quase cinco anos na Companhia de Estágios, transitando entre um agente de IA para
recrutamento construído em Node.js com a API da OpenAI, uma reescrita de uma integração de assinatura
eletrônica para arquitetura hexagonal, e uma reescrita de query que levou um job de faturamento de
gigabytes de memória e minutos de execução para kilobytes e milissegundos. Também já trabalhei com big
data (Spark, cloud híbrida), sistemas financeiros (C#/.NET) e APIs backend em Laravel e PHP.

Gosto de problemas em que a solução é estrutural, não um remendo. Se você lida com infraestrutura
espalhada, automação instável ou um backend que já cresceu além do design original, me chama.

## Bullets de experiência (para cada cargo)

### Intelligenti Stefanini | Sr. Automation Engineer
- Arquitetei um SDK em Python que unificou a execução assíncrona de jobs entre serviços de RPA,
  reduzindo a configuração por serviço de web driver, logging e consumidor do RabbitMQ a um runtime
  compartilhado adotado por padrão (10 de 32 robôs legados já migrados, 22 restantes).
- Construí serviços de RPA containerizados para a área jurídica em cima do SDK: consumo de RabbitMQ,
  APIs REST do Odoo ERP, web scraping e resolução automatizada de captcha.
- Implantei OpenTelemetry de ponta a ponta e entreguei dashboards no Grafana que o time passou a
  checar antes de um incidente virar chamado.
- Entreguei uma TUI em Go para monitoramento de ociosidade de hosts em tempo real, usada para decidir
  quais hosts reduzir.

### Companhia de Estágios (um único card de empresa, dois cargos empilhados, 4 anos e 9 meses no total)

O LinkedIn permite múltiplos cargos dentro de uma mesma empresa. Use essa estrutura em vez de um único
cargo mesclado: ela mostra a promoção de forma explícita e ainda soma o tempo total no card da empresa.

#### Cargo 1: Software Engineer | Jul 2022 - Mai 2026 (3 anos e 11 meses)
- Entreguei um agente de IA para recrutamento (Node.js, Next.js, API da OpenAI) que substituiu uma
  interface de filtros confusa por busca em linguagem natural na base de candidatos.
- Redesenhei uma integração de assinatura eletrônica para arquitetura hexagonal, desacoplando APIs de
  fornecedor da regra de negócio e reduzindo o tempo de integração e teste de futuros fornecedores.
- Reescrevi um job de faturamento cheio de queries N+1 em uma única query: memória caiu de mais de
  1GB para kilobytes, execução de minutos para milissegundos.
- Automatizei um fluxo de envio de dados de compliance para o governo, reduzindo um dia inteiro de
  trabalho manual para menos de 3 minutos.

#### Cargo 2: Estagiário de Engenharia de Software | Set 2021 - Jul 2022 (11 meses)
Sem bullets de descrição necessários, é assim que a maioria dos perfis de estágio-para-efetivação
aparece no LinkedIn. Em vez disso, associe as competências de base (ex.: JavaScript, Linux, PHP) para o
cargo não ficar vazio, sem atribuir conquistas específicas que não dá para datar com certeza dentro da
janela do estágio.

### Freelance | Backend Consultant
- Lumini: construí uma ponte Laravel com o ERP TOTVS Protheus para gestão de vendas e produção.
- Intelligenti: construí um pipeline de RPA em Python paralelizado para ingestão de contratos de
  crédito em PDF, com logging estruturado de métricas.

### ScanSource | Product Analyst & Automation Engineer
- Automatizei extração de relatórios financeiros corporativos em Python, reduzindo um processo de 3
  horas para 3 minutos.
- Liderei a internacionalização de um CRM Salesforce para uma nova unidade de negócio, trabalhando
  diretamente com stakeholders nos Estados Unidos.

### Keyrus | Big Data Engineer
- Construí pipelines de ETL e otimizei modelos de dados em multi-cloud híbrida (Cloudera, Azure, GCP)
  com Scala, Python e Apache Spark.

## Seção de projetos

- **Distributed Payment System** (em construção): sistema de pagamentos baseado em microsserviços,
  focado em integridade de dados e disponibilidade durante falhas parciais. Go, C#, Docker, Kafka,
  PostgreSQL, TypeScript, RPC, REST.
- **Voice Agent** (em construção): pipeline de voz em tempo real (captura, transcrição, LLM, síntese),
  construído para entender como funciona a interação por voz com LLMs de ponta a ponta. Python, Ollama,
  faster-whisper, piper-tts.
- **Personal Financial Management System** (em construção): plataforma financeira containerizada para
  hierarquia de contas e rastreamento de transações, rodando na BEAM VM por concorrência e tolerância a
  falhas. Elixir, Phoenix, Ecto, Docker, PostgreSQL.

## Top 3 competências para fixar

O LinkedIn só destaca 3 competências em evidência (o painel "Top Skills" visto no PDF exportado), então
essa lista fica limitada a 3, sem inflar para 4-5 como uma lista geral de Competências poderia ter.

1. Python
2. Docker
3. Observabilidade / SRE

Decisão do Arthur: priorizar Python e Docker em vez de Kubernetes, já que Kubernetes não é uma
competência que ele considera forte. Aparece no stack da Intelligenti Stefanini, mas não é algo que ele
quer representar como competência central. Fixá-lo mesmo assim correria o mesmo risco de
superestimação que o Kafka antes. Python e Docker têm anos de uso real e profundo em quase todos os
cargos, por isso são a escolha mais sólida para fixar. Observabilidade/SRE fica com a terceira vaga,
respaldada pelo trabalho com OpenTelemetry/Grafana/Loki, o sinal mais sênior/platform entre as
competências reais.

System design também é um termo adicional forte, respaldado pela arquitetura do SDK, pela reescrita em
arquitetura hexagonal e agora por um curso real (o "Descomplicando o System Design" da LinuxTips,
listado em Certificações). Só não entrou no corte de 3 vagas fixadas; adicione à lista geral de
Competências do perfil.

Kubernetes não sai do perfil, continua correto como item da seção geral de Competências (stack da
Intelligenti Stefanini), só não é uma das 3 fixadas que aparecem no topo.

Apache Kafka foi deixado de fora de propósito: só aparece no projeto Distributed Payment System, não em
nenhum emprego, então fixá-lo como competência central superestimaria sua experiência real. Ele
permanece na descrição daquele projeto, onde já está correto, em vez de na lista de competências do
perfil.
