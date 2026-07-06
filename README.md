<div align="center">

**English** | [Türkçe](README.tr.md)

</div>

<div align="center">

# Orhan Yarkın

**Software Engineer — Real-Time Systems for Financial Markets**

[![Location](https://img.shields.io/badge/Istanbul,_Turkey-4f46e5?style=for-the-badge&logo=googlemaps&logoColor=white)](https://github.com/orhanyarkin)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0a66c2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/orhanyarkin)
[![Email](https://img.shields.io/badge/orhanyarkin@gmail.com-6366f1?style=for-the-badge&logo=gmail&logoColor=white)](mailto:orhanyarkin@gmail.com)

</div>

---

## About

I build real-time systems for financial markets. For the last 2.5 years I've been developing **InfoX**, a mobile trading app for the BIST and US markets — owning features end to end, from architecture to production.

- Run **15+ .NET microservices** serving live market data to thousands of concurrent users
- Built the real-time market data feed: **WebSocket → RabbitMQ → SignalR**, with automatic primary/fallback failover per trading session
- Handle market-open spikes of **100,000+ messages/second** without loss (bounded queues, backpressure, .NET Channels)
- Built the full fundamental analysis module: Hangfire jobs pull data from KAP, TEFAS and the Central Bank; a Strategy-pattern parser turns bank, insurance and industrial statements into **1,000+ metrics**
- Shipped an AI feature that translates US market news into Turkish (OpenAI), translated once and served from Redis to keep costs low
- Cut database load **~60%** with Redis caching; Circuit Breaker + Retry so one failing call can't cascade

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
![Jenkins](https://img.shields.io/badge/Jenkins-d24939?style=flat-square&logo=jenkins&logoColor=white)
![ArgoCD](https://img.shields.io/badge/ArgoCD-ef7b4d?style=flat-square&logo=argo&logoColor=white)
![Grafana](https://img.shields.io/badge/Grafana-f46800?style=flat-square&logo=grafana&logoColor=white)
![Kibana](https://img.shields.io/badge/Kibana-005571?style=flat-square&logo=kibana&logoColor=white)

---

## Featured Projects

### [tickforge-go](https://github.com/orhanyarkin/tickforge-go) — Multi-Exchange L2 Order Book Engine

Builds a consistent Level-2 order book from live **Binance** and **Coinbase** feeds.

| | |
|---|---|
| **Correctness** | Snapshot bootstrap, gap detection, automatic resync |
| **Concurrency** | Race-free by design — one goroutine owns each book, readers see an immutable snapshot via an atomic pointer, verified with Go's race detector in CI |
| **Performance** | Hand-written allocation-free JSON scanner: **0 allocs/frame, ~8× faster** than `encoding/json` |
| **Measurement** | Honest tick-to-process latency, p50/p99 via HdrHistogram, reproducible benchmarks |
| **Delivery** | Distroless Docker image, GitHub Actions CI |

> The original .NET prototype lives in [TickForge](https://github.com/orhanyarkin/TickForge) — the Go rewrite is where active development happens.

### [search-engine-service](https://github.com/orhanyarkin/search-engine-service) — Multi-Provider Search Engine (.NET 10)

A search service that ingests data from multiple content providers (JSON & XML), normalizes it, ranks results with a weighted scoring algorithm, and serves them over a REST API. Built as a company case study against mock provider APIs.

| | |
|---|---|
| **Architecture** | Clean Architecture (4 layers), CQRS with MediatR, JWT auth |
| **Search** | Elasticsearch with BM25 relevance, fuzzy matching, prefix & wildcard queries |
| **Data** | PostgreSQL (EF Core, code-first) + Redis cache via the Decorator pattern with key-prefix invalidation |
| **Events** | RabbitMQ + MassTransit — async cache invalidation and reindexing after sync |
| **Quality** | xUnit + Moq + FluentAssertions; one-command `docker-compose` bringing up all 5 services |

### [finance-uni-club](https://github.com/orhanyarkin/finance-uni-club) — Startup & Finance Community Platform

Community platform I built and run end to end for a university startup & finance club — live in production at [startupvefinanstoplulugu.com](https://www.startupvefinanstoplulugu.com).

- **Next.js 14 + TypeScript + Sanity CMS**, built for SEO and performance
- Deployed on **Vercel** with CI/CD and automatic preview builds on every pull request

---

## GitHub

<div align="center">

[![Top Languages](https://github-readme-stats.vercel.app/api/top-langs/?username=orhanyarkin&layout=compact&theme=tokyonight&hide_border=true&bg_color=0d1117&cache_seconds=86400)](https://github.com/orhanyarkin?tab=repositories)

</div>

---

## Currently

```yaml
building:   tickforge-go — pushing the hot path toward zero allocations
learning:   market microstructure, exchange feed protocols (ITCH/SBE), Go internals
open_to:    fintech · low-latency systems · backend engineering · remote
```

---

<div align="center">

**"Willing to question defaults and rebuild from first principles."**

[![LinkedIn](https://img.shields.io/badge/Connect_on_LinkedIn-0a66c2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/orhanyarkin)
[![Email](https://img.shields.io/badge/Say_Hello-6366f1?style=for-the-badge&logo=gmail&logoColor=white)](mailto:orhanyarkin@gmail.com)

</div>
