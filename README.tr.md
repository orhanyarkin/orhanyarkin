<div align="center">

[English](README.md) | **Türkçe**

</div>

<div align="center">

# Orhan Yarkın

**Yazılım Mühendisi — Finansal Piyasalar için Gerçek Zamanlı Sistemler**

[![Konum](https://img.shields.io/badge/İstanbul,_Türkiye-4f46e5?style=for-the-badge&logo=googlemaps&logoColor=white)](https://github.com/orhanyarkin)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0a66c2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/orhanyarkin)
[![Email](https://img.shields.io/badge/orhanyarkin@gmail.com-6366f1?style=for-the-badge&logo=gmail&logoColor=white)](mailto:orhanyarkin@gmail.com)

</div>

---

## Hakkımda

Finansal piyasalar için gerçek zamanlı sistemler geliştiriyorum. Son 2,5 yıldır BIST ve ABD piyasaları için bir mobil trading uygulaması olan **InfoX** üzerinde çalışıyorum — özellikleri mimariden production'a uçtan uca sahiplenerek.

- Binlerce eşzamanlı kullanıcıya canlı piyasa verisi sunan **15+ .NET mikroservisi** geliştiriyor ve işletiyorum
- Gerçek zamanlı piyasa veri akışını kurdum: **WebSocket → RabbitMQ → SignalR**, seans bazlı otomatik primary/fallback failover ile
- Piyasa açılışındaki **saniyede 100.000+ mesajlık** yükü kayıpsız karşılıyorum (bounded queue, backpressure, .NET Channels)
- Temel analiz modülünün tamamını geliştirdim: Hangfire job'ları KAP, TEFAS ve TCMB'den veri toplar; Strategy pattern tabanlı bir parser banka, sigorta ve sanayi bilançolarını **1.000+ metriğe** dönüştürür
- ABD piyasa haberlerini Türkçeye çeviren bir AI özelliği yayına aldım (OpenAI) — her haber bir kez çevrilip Redis'ten sunularak maliyet düşük tutulur
- Redis cache ile veritabanı yükünü **~%60** azalttım; Circuit Breaker + Retry ile tek bir hatalı çağrının zincirleme çökmeye yol açması engellendi

**Açığım:** fintech, düşük gecikmeli sistemler ve backend mühendisliği alanlarında uluslararası roller (remote uyumlu).

---

## Teknolojiler

**Diller & Framework'ler**

![C#](https://img.shields.io/badge/C%23-512bd4?style=flat-square&logo=dotnet&logoColor=white)
![.NET](https://img.shields.io/badge/.NET_6--10-512bd4?style=flat-square&logo=dotnet&logoColor=white)
![Go](https://img.shields.io/badge/Go-00add8?style=flat-square&logo=go&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178c6?style=flat-square&logo=typescript&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-f7df1e?style=flat-square&logo=javascript&logoColor=black)

**Mesajlaşma & Gerçek Zamanlı**

![RabbitMQ](https://img.shields.io/badge/RabbitMQ-ff6600?style=flat-square&logo=rabbitmq&logoColor=white)
![SignalR](https://img.shields.io/badge/SignalR-512bd4?style=flat-square&logo=dotnet&logoColor=white)
![WebSocket](https://img.shields.io/badge/WebSocket-4f46e5?style=flat-square&logo=socketdotio&logoColor=white)
![Hangfire](https://img.shields.io/badge/Hangfire-2d3748?style=flat-square&logo=dotnet&logoColor=white)

**Veri & Cache**

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

## Öne Çıkan Projeler

### [tickforge-go](https://github.com/orhanyarkin/tickforge-go) — Çoklu Borsa L2 Order Book Motoru

Canlı **Binance** ve **Coinbase** feed'lerinden tutarlı bir Level-2 order book kurar.

| | |
|---|---|
| **Doğruluk** | Snapshot bootstrap, gap tespiti, otomatik resync |
| **Eşzamanlılık** | Tasarım gereği race-free — her book'u tek bir goroutine sahiplenir, okuyucular immutable snapshot'ı atomic pointer üzerinden okur; Go'nun race detector'ı CI'da doğrular |
| **Performans** | Elle yazılmış allocation-free JSON scanner: **frame başına 0 alloc, `encoding/json`'a göre ~8× hızlı** |
| **Ölçüm** | Dürüst tick-to-process gecikmesi, HdrHistogram ile p50/p99, tekrar üretilebilir benchmark'lar |
| **Dağıtım** | Distroless Docker imajı, GitHub Actions CI |

> Orijinal .NET prototipi [TickForge](https://github.com/orhanyarkin/TickForge) reposunda — aktif geliştirme Go tarafında.

### [search-engine-service](https://github.com/orhanyarkin/search-engine-service) — Çoklu Sağlayıcılı Arama Motoru (.NET 10)

Birden fazla content provider'dan (JSON & XML) veri çeken, normalize eden, weighted scoring algoritmasıyla puanlayan ve REST API üzerinden sunan bir arama servisi. Mock provider API'lerine karşı bir şirket case study'si olarak geliştirildi.

| | |
|---|---|
| **Mimari** | Clean Architecture (4 katman), MediatR ile CQRS, JWT auth |
| **Arama** | Elasticsearch — BM25 relevance, fuzzy match, prefix & wildcard sorgular |
| **Veri** | PostgreSQL (EF Core, code-first) + Decorator pattern ile Redis cache, key-prefix invalidation |
| **Event'ler** | RabbitMQ + MassTransit — sync sonrası async cache invalidation ve reindex |
| **Kalite** | xUnit + Moq + FluentAssertions; tek komutla 5 servisi ayağa kaldıran `docker-compose` |

### [finance-uni-club](https://github.com/orhanyarkin/finance-uni-club) — Startup & Finans Topluluğu Platformu

Bir üniversite startup & finans topluluğu için uçtan uca geliştirip işlettiğim platform — [startupvefinanstoplulugu.com](https://www.startupvefinanstoplulugu.com) adresinde canlı.

- **Next.js + TypeScript + Sanity CMS**, SEO ve performans odaklı
- **Vercel** üzerinde CI/CD, her pull request'te otomatik preview build

---

## GitHub

<div align="center">

![Top Languages](https://github-readme-stats.vercel.app/api/top-langs/?username=orhanyarkin&layout=compact&theme=tokyonight&hide_border=true&bg_color=0d1117)

</div>

---

## Şu Sıralar

```yaml
geliştiriyorum:  tickforge-go — hot path'i sıfır allocation'a yaklaştırma
öğreniyorum:     piyasa mikroyapısı, borsa feed protokolleri (ITCH/SBE), Go internals
açığım:          fintech · düşük gecikmeli sistemler · backend mühendisliği · remote
```

---

<div align="center">

**"Varsayılanları sorgulayıp gerektiğinde ilk prensiplerden yeniden kurmaya hazır."**

[![LinkedIn](https://img.shields.io/badge/LinkedIn'de_Bağlan-0a66c2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/orhanyarkin)
[![Email](https://img.shields.io/badge/Merhaba_De-6366f1?style=for-the-badge&logo=gmail&logoColor=white)](mailto:orhanyarkin@gmail.com)

</div>
