# Overview
`streaming_infra` contains the local infrastructure stack powering a distributed event-driven sports streaming simulation platform.
This repository is responsible for:
* local infrastructure orchestration
* Docker networking
* Kafka event streaming
* Redis realtime caching
* PostgreSQL persistence
* observability tooling
* future deployment infrastructure

The application layer (Spring Boot services, WebSocket gateway, frontend UIs, etc.) lives in separate repositories.

---

# Architecture
```text
todo
```

---

# Infrastructure Stack
| Technology     | Purpose                  |
| -------------- | ------------------------ |
| Kafka          | Event streaming backbone |
| Redis          | Realtime state + pub/sub |
| PostgreSQL     | Persistent storage       |
| Docker Compose | Local orchestration      |
| Prometheus     | Metrics collection       |
| Grafana        | Metrics visualization    |

---

# Goals
This project is designed to explore:
* distributed systems architecture
* event-driven microservices
* asynchronous processing
* realtime websocket systems
* caching strategies
* observability
* scalable backend design
* local infrastructure orchestration

---

# Repository Structure
```text
streaming_infra/
│
├── docker-compose.yml
├── .env.example
├── .gitignore
└── README.md
```

---

# Services Expected To Connect
The following external services are expected to connect to this infrastructure stack:
* simulation-service
* score-service
* fantasy-service
* analytics-service
* websocket-service
* admin-ui
* client-ui

---

# Local Development

## Prerequisites
* Docker Desktop
* Docker Compose
* Java 26+
* IntelliJ IDEA (recommended)

## Environment Setup
Copy the example environment file before starting:
```bash
cp .env.example .env
```

The `.env` file is gitignored and should never be committed. Default values in `.env.example` work out of the box for local development — update them if you need custom credentials.

| Variable            | Description              |
| ------------------- | ------------------------ |
| `POSTGRES_USER`     | PostgreSQL username      |
| `POSTGRES_PASSWORD` | PostgreSQL password      |
| `POSTGRES_DB`       | PostgreSQL database name |

---

# Starting Infrastructure
```bash
docker compose up -d
```

---

# Stopping Infrastructure
```bash
docker compose down
```

To also remove all volumes (wipes persisted data):
```bash
docker compose down -v
```

---

# Planned Components

## Kafka Topics
```text
game-events
score-events
fantasy-events
```

---

# Planned Observability
Prometheus + Grafana dashboards for:
* Kafka consumer lag
* events/sec
* websocket connections
* Redis cache metrics
* API latency
* JVM metrics

---