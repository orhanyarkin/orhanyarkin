<div align="center">

**English** | [Türkçe](README.tr.md)

</div>

<div align="center">

# Orhan Yarkın

**Software Engineer | Backend & Real-Time Market Data (C#, .NET)**

[![Location](https://img.shields.io/badge/Istanbul,_Turkey-4f46e5?style=for-the-badge&logo=googlemaps&logoColor=white)](https://github.com/orhanyarkin)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0a66c2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/orhanyarkin)
[![Email](https://img.shields.io/badge/orhanyarkin@gmail.com-6366f1?style=for-the-badge&logo=gmail&logoColor=white)](mailto:orhanyarkin@gmail.com)

</div>

---

## About

I build backend systems for financial markets. For nearly 3 years I've been working on **InfoX**, a mobile trading app for the BIST and US markets, at a brokerage in Istanbul. Most of my work is real-time market data, provider integrations and keeping things stable at market open.

- Develop and run **C# / .NET** services in a microservice architecture of 30+ services, from development to monitoring and incident response
- Integrated BIST and US market data providers over **REST and WebSocket**, with retries, circuit breakers and automatic failover between providers
- Reworked the real-time price distribution service (**RabbitMQ → SignalR**) so a slow client can't delay the others at market open
- Migrated US market data to a new provider without changing the mobile API contract. Serving snapshots from memory cut response times from hundreds of milliseconds to **under 30 ms**
- Built the fundamental analysis and stock screening module from scratch to production. Hangfire jobs pull data from KAP, TEFAS and the Central Bank, and a Strategy-pattern parser turns bank, insurance and industrial statements into **1,000+ metrics**
- Built an LLM feature that translates US market news into Turkish with the OpenAI API, using batching, JSON output and Redis caching to keep cost low
- Cut database load by **~60%** with Redis caching and request coalescing

---

## Tech Stack

**Languages & Frameworks**

![C#](https://img.shields.io/badge/C%23-512bd4?style=flat-square&logo=dotnet&logoColor=white)
![.NET](https://img.shields.io/badge/.NET_6--10-512bd4?style=flat-square&logo=dotnet&logoColor=white)
![Go](https://img.shields.io/badge/Go-00add8?style=flat-square&logo=go&logoColor=white)
![Java](https://img.shields.io/badge/Java-e76f00?style=flat-square&logo=openjdk&logoColor=white)
![Spring Boot](https://img.shields.io/badge/Spring_Boot-6db33f?style=flat-square&logo=springboot&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178c6?style=flat-square&logo=typescript&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-f7df1e?style=flat-square&logo=javascript&logoColor=black)

**Messaging & Real-Time**

![RabbitMQ](https://img.shields.io/badge/RabbitMQ-ff6600?style=flat-square&logo=rabbitmq&logoColor=white)
![Kafka](https://img.shields.io/badge/Kafka-231f20?style=flat-square&logo=apachekafka&logoColor=white)
![SignalR](https://img.shields.io/badge/SignalR-512bd4?style=flat-square&logo=dotnet&logoColor=white)
![WebSocket](https://img.shields.io/badge/WebSocket-4f46e5?style=flat-square&logo=socketdotio&logoColor=white)
![Hangfire](https://img.shields.io/badge/Hangfire-2d3748?style=flat-square&logo=dotnet&logoColor=white)

**Data & Caching**

![Redis](https://img.shields.io/badge/Redis-dc382d?style=flat-square&logo=redis&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169e1?style=flat-square&logo=postgresql&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479a1?style=flat-square&logo=mysql&logoColor=white)
![Elasticsearch](https://img.shields.io/badge/Elasticsearch-005571?style=flat-square&logo=elasticsearch&logoColor=white)

**Cloud & DevOps**

![Docker](https://img.shields.io/badge/Docker-2496ed?style=flat-square&logo=docker&logoColor=white)
![Kubernetes](https://img.shields.io/badge/Kubernetes-326ce5?style=flat-square&logo=kubernetes&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-232f3e?style=flat-square&logo=amazonwebservices&logoColor=white)
![Terraform](https://img.shields.io/badge/Terraform-7b42bc?style=flat-square&logo=terraform&logoColor=white)
![Jenkins](https://img.shields.io/badge/Jenkins-d24939?style=flat-square&logo=jenkins&logoColor=white)
![ArgoCD](https://img.shields.io/badge/ArgoCD-ef7b4d?style=flat-square&logo=argo&logoColor=white)
![Grafana](https://img.shields.io/badge/Grafana-f46800?style=flat-square&logo=grafana&logoColor=white)
![Kibana](https://img.shields.io/badge/Kibana-005571?style=flat-square&logo=kibana&logoColor=white)

**AI**

![OpenAI API](https://img.shields.io/badge/OpenAI_API-412991?style=flat-square&logo=openai&logoColor=white)
![Spring AI](https://img.shields.io/badge/Spring_AI-6db33f?style=flat-square&logo=spring&logoColor=white)

---

## Featured Projects

### [saiman](https://github.com/orhanyarkin/saiman) | Agentic Payments Platform (Java, Spring Boot, AWS)

AI agents pay for the data they use with **USDC** over the **x402** protocol on Base Sepolia.

| | |
|---|---|
| **Agents** | Planner, researcher, risk and synthesis agents on Spring AI, with spend limits enforced in code |
| **Payments** | x402 pay-per-request, USDC on Base Sepolia, reconciled against the chain |
| **Ledger** | Double-entry ledger fed through Kafka with an outbox, always balanced |
| **Delivery** | Java 25, Spring Boot, Testcontainers, deployed on AWS (ECS, RDS) with Terraform |

### [tickforge-go](https://github.com/orhanyarkin/tickforge-go) | Multi-Exchange L2 Order Book Engine (Go)

Builds a consistent Level-2 order book from live **Binance** and **Coinbase** feeds.

| | |
|---|---|
| **Correctness** | Snapshot bootstrap, gap detection, automatic resync |
| **Concurrency** | Race-free by design. One goroutine owns each book and readers see an immutable snapshot through an atomic pointer, checked with Go's race detector in CI |
| **Performance** | Hand-written allocation-free JSON scanner, **0 allocs/frame and ~8× faster** than `encoding/json` |
| **Measurement** | Tick-to-process latency with p50/p99 via HdrHistogram, reproducible benchmarks |
| **Delivery** | Distroless Docker image, GitHub Actions CI |

> The original .NET version lives in [TickForge](https://github.com/orhanyarkin/TickForge). Active development happens in the Go rewrite.

### [search-engine-service](https://github.com/orhanyarkin/search-engine-service) | Multi-Provider Search Engine (.NET 10)

A search service that ingests data from multiple content providers (JSON and XML), normalizes it, ranks results with a weighted scoring algorithm and serves them over a REST API. Built as a company case study against mock provider APIs.

| | |
|---|---|
| **Architecture** | Clean Architecture (4 layers), CQRS with MediatR, JWT auth |
| **Search** | Elasticsearch with BM25 relevance, fuzzy matching, prefix and wildcard queries |
| **Data** | PostgreSQL (EF Core, code-first) and a Redis cache through the Decorator pattern with key-prefix invalidation |
| **Events** | RabbitMQ and MassTransit for async cache invalidation and reindexing after sync |
| **Quality** | xUnit, Moq and FluentAssertions, one `docker-compose` command brings up all 5 services |

### [finance-uni-club](https://github.com/orhanyarkin/finance-uni-club) | Startup & Finance Community Website

Website I designed and built on my own for the Startup & Finance Community at Ankara Medipol University, live at [startupvefinanstoplulugu.com](https://startupvefinanstoplulugu.com).

- **Next.js 16, TypeScript and Sanity CMS**, with blog, events and team pages in Turkish and English
- Data hub with macroeconomic data from the **TCMB EVDS** and **World Bank** APIs, charted with Recharts
- Deployed on **Vercel** with preview builds on every pull request

---

<div align="center">

[![LinkedIn](https://img.shields.io/badge/Connect_on_LinkedIn-0a66c2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/orhanyarkin)
[![Email](https://img.shields.io/badge/Say_Hello-6366f1?style=for-the-badge&logo=gmail&logoColor=white)](mailto:orhanyarkin@gmail.com)

</div>
