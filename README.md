# 🔭 Observability Stack

A complete, fully local observability platform built with Docker Compose.

**Covers all 3 pillars of observability:**
- 📊 **Metrics** — Prometheus + Node Exporter
- 📜 **Logs** — Loki + Promtail
- 🔍 **Traces** — Jaeger
- 🖥️ **Visualization** — Grafana (unified dashboard)

---

## 🚀 How to Run

### Prerequisites
- [Docker Desktop](https://www.docker.com/products/docker-desktop/) installed and running

### Start the stack
```bash
docker-compose up -d
```

First run will download images (~5 minutes). After that, it starts in seconds.

### Stop the stack
```bash
docker-compose down
```

---

## 🌐 Access URLs

| Tool | URL | Credentials |
|------|-----|-------------|
| **Grafana** | http://localhost:3000 | admin / admin |
| **Prometheus** | http://localhost:9090 | — |
| **Jaeger UI** | http://localhost:16686 | — |
| **Loki** | http://localhost:3100 | — |
| **Node Exporter** | http://localhost:9100/metrics | — |

---

## 📊 Import a Dashboard in Grafana

1. Open http://localhost:3000 → login with admin/admin
2. Click **Dashboards** → **Import**
3. Enter Dashboard ID **`1860`** → click **Load**
4. Select **Prometheus** as the data source → click **Import**

You'll see live CPU, memory, disk, and network metrics instantly!

---

## 🏗️ Project Structure

```
observability-stack/
├── docker-compose.yml                         # Orchestrates all services
├── prometheus/
│   └── prometheus.yml                         # Scrape config
├── loki/
│   └── loki-config.yml                        # Log storage config
├── promtail/
│   └── promtail-config.yml                    # Log collector config
└── grafana/
    └── provisioning/
        ├── datasources/datasources.yml        # Auto-connects data sources
        └── dashboards/dashboards.yml          # Dashboard loader config
```

---

## 🧰 Tech Stack

| Tool | Role | Port |
|------|------|------|
| Prometheus | Metrics scraping & storage | 9090 |
| Node Exporter | System metrics exporter | 9100 |
| Loki | Log aggregation | 3100 |
| Promtail | Log collector agent | 9080 |
| Jaeger | Distributed tracing | 16686 |
| Grafana | Visualization & dashboards | 3000 |

---

## 💡 Resume Line

> Built full observability platform (metrics, logs, and traces) using Prometheus, Loki, Jaeger, and Grafana via Docker Compose.

---

## 📄 License

MIT
