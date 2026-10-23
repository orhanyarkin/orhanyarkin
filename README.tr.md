<div align="center">

[English](README.md) | **Türkçe**

</div>

<div align="center">

# Orhan Yarkın

**Yazılım Mühendisi | Backend ve Gerçek Zamanlı Piyasa Verisi (C#, .NET)**

[![Konum](https://img.shields.io/badge/İstanbul,_Türkiye-4f46e5?style=for-the-badge&logo=googlemaps&logoColor=white)](https://github.com/orhanyarkin)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0a66c2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/orhanyarkin)
[![Email](https://img.shields.io/badge/orhanyarkin@gmail.com-6366f1?style=for-the-badge&logo=gmail&logoColor=white)](mailto:orhanyarkin@gmail.com)

</div>

---

## Hakkımda

Finansal piyasalar için backend sistemleri geliştiriyorum. 3 yıla yakın süredir İstanbul'da bir aracı kurumda, BIST ve ABD piyasalarında işlem yapılan mobil yatırım uygulaması **InfoX** üzerinde çalışıyorum. İşimin büyük kısmı gerçek zamanlı piyasa verisi, veri sağlayıcı entegrasyonları ve seans açılışlarında sistemi ayakta tutmak.

- 30'dan fazla servisten oluşan mikroservis mimarisinde **C# / .NET** servislerini geliştirmeden izlemeye ve sorunlara müdahaleye kadar yönetiyorum
- BIST ve ABD piyasa verisi sağlayıcılarını **REST ve WebSocket** üzerinden entegre ettim, retry, circuit breaker ve sağlayıcılar arası otomatik failover ekledim
- Gerçek zamanlı fiyat dağıtım servisini (**RabbitMQ → SignalR**) yeniden ele aldım, seans açılışında yavaş bir istemcinin diğerlerini geciktirmesini önledim
- ABD piyasa verisini mobil uygulamanın API sözleşmesini değiştirmeden yeni bir sağlayıcıya taşıdım. Anlık verileri bellekten sunarak yanıt süresini yüzlerce milisaniyeden **30 ms'nin altına** indirdim
- Temel analiz ve hisse filtreleme modülünü sıfırdan canlıya kadar geliştirdim. Hangfire görevleri KAP, TEFAS ve TCMB'den veri topluyor, Strategy pattern tabanlı bir parser banka, sigorta ve sanayi bilançolarını **1.000'den fazla metriğe** dönüştürüyor
- OpenAI API ile ABD piyasa haberlerini Türkçeye çeviren bir LLM özelliği geliştirdim. Maliyeti düşük tutmak için toplu istek, JSON çıktı ve Redis önbelleği kullandım
- Redis önbelleği ve istek birleştirme ile veritabanı yükünü **yaklaşık %60** azalttım

---

## Teknolojiler

**Diller ve Framework'ler**

![C#](https://img.shields.io/badge/C%23-512bd4?style=flat-square&logo=dotnet&logoColor=white)
![.NET](https://img.shields.io/badge/.NET_6--10-512bd4?style=flat-square&logo=dotnet&logoColor=white)
![Go](https://img.shields.io/badge/Go-00add8?style=flat-square&logo=go&logoColor=white)
![Java](https://img.shields.io/badge/Java-e76f00?style=flat-square&logo=openjdk&logoColor=white)
![Spring Boot](https://img.shields.io/badge/Spring_Boot-6db33f?style=flat-square&logo=springboot&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178c6?style=flat-square&logo=typescript&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-f7df1e?style=flat-square&logo=javascript&logoColor=black)

**Mesajlaşma ve Gerçek Zamanlı**

![RabbitMQ](https://img.shields.io/badge/RabbitMQ-ff6600?style=flat-square&logo=rabbitmq&logoColor=white)
![Kafka](https://img.shields.io/badge/Kafka-231f20?style=flat-square&logo=apachekafka&logoColor=white)
![SignalR](https://img.shields.io/badge/SignalR-512bd4?style=flat-square&logo=dotnet&logoColor=white)
![WebSocket](https://img.shields.io/badge/WebSocket-4f46e5?style=flat-square&logo=socketdotio&logoColor=white)
![Hangfire](https://img.shields.io/badge/Hangfire-2d3748?style=flat-square&logo=dotnet&logoColor=white)

**Veri ve Önbellek**

![Redis](https://img.shields.io/badge/Redis-dc382d?style=flat-square&logo=redis&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169e1?style=flat-square&logo=postgresql&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479a1?style=flat-square&logo=mysql&logoColor=white)
![Elasticsearch](https://img.shields.io/badge/Elasticsearch-005571?style=flat-square&logo=elasticsearch&logoColor=white)

**Cloud ve DevOps**

![Docker](https://img.shields.io/badge/Docker-2496ed?style=flat-square&logo=docker&logoColor=white)
![Kubernetes](https://img.shields.io/badge/Kubernetes-326ce5?style=flat-square&logo=kubernetes&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-232f3e?style=flat-square&logo=amazonwebservices&logoColor=white)
![Terraform](https://img.shields.io/badge/Terraform-7b42bc?style=flat-square&logo=terraform&logoColor=white)
![Jenkins](https://img.shields.io/badge/Jenkins-d24939?style=flat-square&logo=jenkins&logoColor=white)
![ArgoCD](https://img.shields.io/badge/ArgoCD-ef7b4d?style=flat-square&logo=argo&logoColor=white)
![Grafana](https://img.shields.io/badge/Grafana-f46800?style=flat-square&logo=grafana&logoColor=white)
![Kibana](https://img.shields.io/badge/Kibana-005571?style=flat-square&logo=kibana&logoColor=white)

**Yapay Zeka**

![OpenAI API](https://img.shields.io/badge/OpenAI_API-412991?style=flat-square&logo=openai&logoColor=white)
![Spring AI](https://img.shields.io/badge/Spring_AI-6db33f?style=flat-square&logo=spring&logoColor=white)

---

## Öne Çıkan Projeler

### [saiman](https://github.com/orhanyarkin/saiman) | Agentic Ödeme Platformu (Java, Spring Boot, AWS)

Yapay zeka ajanlarının kullandıkları veri için Base Sepolia üzerinde **x402** protokolüyle **USDC** ödediği bir platform.

| | |
|---|---|
| **Ajanlar** | Spring AI üzerinde planlayıcı, araştırmacı, risk ve sentez ajanları, harcama limitleri kodla denetleniyor |
| **Ödemeler** | x402 ile istek başına ödeme, Base Sepolia üzerinde USDC, zincirle karşılaştırma |
| **Defter** | Kafka ve outbox ile beslenen, her zaman dengede kalan çift taraflı kayıt defteri (ledger) |
| **Dağıtım** | Java 25, Spring Boot, Testcontainers, Terraform ile AWS'ye (ECS, RDS) kurulum |

### [tickforge-go](https://github.com/orhanyarkin/tickforge-go) | Çok Borsalı L2 Order Book Motoru (Go)

Canlı **Binance** ve **Coinbase** akışlarından tutarlı bir Level-2 order book oluşturur.

| | |
|---|---|
| **Doğruluk** | Snapshot ile başlangıç, eksik güncelleme tespiti, otomatik yeniden senkronizasyon |
| **Eşzamanlılık** | Tasarım gereği race condition yok. Her book'un sahibi tek bir goroutine, okuyucular atomic pointer üzerinden değişmez snapshot görüyor. CI'da Go'nun race detector'ı ile doğrulanıyor |
| **Performans** | Elle yazılmış, bellek ayırmayan JSON ayrıştırıcı. **Frame başına 0 allocation**, `encoding/json`'dan **yaklaşık 8 kat hızlı** |
| **Ölçüm** | HdrHistogram ile p50/p99 tick-to-process gecikmesi, tekrarlanabilir benchmark'lar |
| **Dağıtım** | Distroless Docker imajı, GitHub Actions CI |

> İlk .NET sürümü [TickForge](https://github.com/orhanyarkin/TickForge) reposunda. Aktif geliştirme Go sürümünde devam ediyor.

### [search-engine-service](https://github.com/orhanyarkin/search-engine-service) | Çok Sağlayıcılı Arama Motoru (.NET 10)

Birden fazla içerik sağlayıcısından (JSON ve XML) veri çeken, normalize eden, ağırlıklı puanlama algoritmasıyla sıralayan ve REST API üzerinden sunan bir arama servisi. Mock sağlayıcı API'lerine karşı bir şirket case study'si olarak geliştirildi.

| | |
|---|---|
| **Mimari** | Clean Architecture (4 katman), MediatR ile CQRS, JWT auth |
| **Arama** | Elasticsearch ile BM25 relevance, fuzzy match, prefix ve wildcard sorgular |
| **Veri** | PostgreSQL (EF Core, code-first) ve Decorator pattern ile Redis önbelleği, key-prefix invalidation |
| **Olaylar** | Senkronizasyon sonrası asenkron önbellek temizleme ve yeniden indeksleme için RabbitMQ ve MassTransit |
| **Kalite** | xUnit, Moq ve FluentAssertions, tek `docker-compose` komutuyla 5 servis ayağa kalkıyor |

### [finance-uni-club](https://github.com/orhanyarkin/finance-uni-club) | Startup ve Finans Topluluğu Web Sitesi

Ankara Medipol Üniversitesi Startup ve Finans Topluluğu için tek başıma tasarlayıp geliştirdiğim web sitesi, [startupvefinanstoplulugu.com](https://startupvefinanstoplulugu.com) adresinde yayında.

- **Next.js 16, TypeScript ve Sanity CMS** ile Türkçe ve İngilizce blog, etkinlik ve ekip sayfaları
- **TCMB EVDS** ve **World Bank** API'lerinden gelen makroekonomik verilerin Recharts ile gösterildiği bir veri merkezi
- **Vercel** üzerinde yayında, her pull request'te preview build alınıyor

---

## GitHub

<div align="center">

[![Top Languages](https://github-readme-stats.vercel.app/api/top-langs/?username=orhanyarkin&layout=compact&theme=tokyonight&hide_border=true&bg_color=0d1117&cache_seconds=86400)](https://github.com/orhanyarkin?tab=repositories)

</div>

---

<div align="center">

[![LinkedIn](https://img.shields.io/badge/LinkedIn'de_Bağlan-0a66c2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/orhanyarkin)
[![Email](https://img.shields.io/badge/Merhaba_De-6366f1?style=for-the-badge&logo=gmail&logoColor=white)](mailto:orhanyarkin@gmail.com)

</div>
