<div align="center">
  <h1>BITS AI Gateway</h1>
  <p>
    <a href="https://ai.bits.co.id">
      <img src="https://img.shields.io/badge/ai.bits.co.id-Online-00C853?style=for-the-badge&logo=statuspage&logoColor=white" alt="ai.bits.co.id Online" />
    </a>
  </p>
  <p>Docker-based AI gateway and routing proxy for secure service access</p>
  <br>
  <p>
    <img src="https://img.shields.io/badge/Docker-2496ED?style=flat&logo=docker&logoColor=white" alt="Docker" />
    <img src="https://img.shields.io/badge/Node.js-339933?style=flat&logo=nodedotjs&logoColor=white" alt="Node.js" />
    <img src="https://img.shields.io/badge/TypeScript-3178C6?style=flat&logo=typescript&logoColor=white" alt="TypeScript" />
    <img src="https://img.shields.io/badge/Observability-111827?style=flat" alt="Observability" />
    <img src="https://img.shields.io/badge/license-MIT-green?style=flat" alt="MIT License" />
  </p>
</div>

---

## Overview

**BITS AI Gateway** is a lightweight Docker deployment for AI traffic routing and proxying. It provides a single entry point for AI services with request handling, auth controls, health checks, and optional observability components.

---

## Features

| Feature | Description |
|---------|-------------|
| **Single Entry Point** | Central endpoint for AI service traffic |
| **API Access Control** | Secret-based request protection |
| **Health Monitoring** | Built-in container health checks |
| **Optional Observability** | Headroom sidecar for metrics and monitoring |
| **Private Search Integration** | Optional SearXNG service support |
| **Docker First** | Runs with Docker Compose only |

## Tech Stack

| Layer | Technology |
|-------|------------|
| **Runtime** | Node.js |
| **Deployment** | Docker, Docker Compose |
| **Protocol** | HTTP |
| **Observability** | Headroom sidecar |
| **Search** | SearXNG |

---

## Project Structure

```text
BITS AI Gateway/
├── .env.example       # Environment template
├── docker-compose.yml # Service definitions
├── README.md          # Project documentation
└── LICENSE            # MIT license
```

---

## Quick Start

### Prerequisites

- Docker
- Docker Compose

### Setup

```bash
git clone https://github.com/BITS-Cloud-Platform/ai.bits.co.id.git
cd ai.bits.co.id
cp .env.example .env
docker compose up -d
```

### Health Check

```bash
curl http://localhost:20128/api/health
```

Expected response:

```json
{"status":"ok"}
```

---

## Configuration

All configuration lives in `.env`.

| Variable | Default | Description |
|----------|---------|-------------|
| `PORT` | `20128` | Application port |
| `NODE_ENV` | `production` | Runtime mode |
| `JWT_SECRET` | required | JWT signing secret |
| `API_KEY_SECRET` | required | API key hashing secret |
| `MACHINE_ID_SALT` | required | Machine ID salt |
| `INITIAL_PASSWORD` | required | Initial admin password |
| `BASE_URL` | — | Public base URL |
| `CLOUD_URL` | — | Cloud endpoint URL |
| `ENABLE_REQUEST_LOGS` | `false` | Enable request logs |
| `OBSERVABILITY_ENABLED` | `true` | Enable monitoring sidecar |
| `AUTH_COOKIE_SECURE` | `true` | Set Secure cookie flag |
| `REQUIRE_API_KEY` | `true` | Require API key on requests |
| `HEADROOM_URL` | `http://headroom:8787` | Headroom service URL |
| `SEARXNG_URL` | `http://searxng:8080/search` | SearXNG endpoint |

---

## Docker Deployment

### Production

```bash
docker compose up -d
```

### Logs

```bash
docker compose logs -f 9router
```

### Stop

```bash
docker compose down
```

### Reset Data

```bash
docker compose down -v
```

---

## Security

- Never commit `.env`
- Use strong random values for all secrets
- Rotate secrets regularly
- Keep `AUTH_COOKIE_SECURE=true` in production
- Restrict network access to exposed ports

---

## Contributing

1. Fork repo
2. Create branch
3. Commit change
4. Open pull request

---

## License

MIT. See `LICENSE`.

<div align="center">
  <p>
    <strong>BITS AI Gateway</strong> ·
    <a href="https://ai.bits.co.id">ai.bits.co.id</a> ·
    <a href="https://bits.co.id">bits.co.id</a>
  </p>
  <p>
    Made with ❤️ by <a href="https://bits.co.id"><strong>Banten IT Solutions</strong></a>
  </p>
</div>
