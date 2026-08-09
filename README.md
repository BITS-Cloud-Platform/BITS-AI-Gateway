<div align="center">
  <h1>BITS AI Gateway</h1>
  <p>
    <a href="https://ai.bits.co.id">
      <img src="https://img.shields.io/badge/BITS%20AI%20Gateway-Online-00C853?style=for-the-badge&logo=statuspage&logoColor=white" alt="BITS AI Gateway Online" />
    </a>
  </p>
  <p>
    Route, secure, and monitor AI traffic through one Docker gateway
  </p>
  <br>
  <p>
    <img src="https://img.shields.io/badge/Docker-2496ED?style=flat&logo=docker&logoColor=white" alt="Docker" />
    <img src="https://img.shields.io/badge/Node.js-339933?style=flat&logo=nodedotjs&logoColor=white" alt="Node.js" />
    <img src="https://img.shields.io/badge/TypeScript-3178C6?style=flat&logo=typescript&logoColor=white" alt="TypeScript" />
    <img src="https://img.shields.io/badge/SearXNG-FFB000?style=flat&logo=search&logoColor=white" alt="SearXNG" />
    <img src="https://img.shields.io/badge/Observability-111827?style=flat" alt="Observability" />
    <img src="https://img.shields.io/badge/license-MIT-green?style=flat" alt="MIT License" />
  </p>
</div>

---

## ✨ Features

| Feature | Description |
|---------|-------------|
| **Single Entry Point** | One endpoint for AI service traffic |
| **Access Control** | API key and JWT-based protection |
| **Health Checks** | Built-in service health monitoring |
| **Optional Observability** | Headroom sidecar for metrics |
| **Private Search Support** | Optional SearXNG integration |
| **Docker Deployment** | Runs with Docker Compose |

## 🛠️ Tech Stack

| Layer | Technology |
|-------|------------|
| **Runtime** | Node.js |
| **Language** | TypeScript |
| **Deployment** | Docker, Docker Compose |
| **Security** | JWT, API key secret, secure cookies |
| **Monitoring** | Headroom sidecar |
| **Search** | SearXNG |

---

## 📁 Project Structure

```text
BITS AI Gateway/
├── .env.example       # Environment template
├── docker-compose.yml # Service definitions
├── README.md          # Project documentation
└── LICENSE            # MIT license
```

---

## 🚀 Quick Start

### Prerequisites

- Docker
- Docker Compose

### Setup

```bash
git clone https://github.com/BITS-Cloud-Platform/bits-ai-gateway.git
cd bits-ai-gateway
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

## 💻 Development

```bash
# View logs
docker compose logs -f 9router

# Restart service
docker compose restart 9router

# Stop all services
docker compose down

# Reset data volume
docker compose down -v
```

---

## ⚙️ Configuration

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

## 🔐 Security

- Never commit `.env`
- Use strong random values for all secrets
- Rotate secrets regularly
- Keep `AUTH_COOKIE_SECURE=true` in production
- Restrict network access to exposed ports

---

## 📄 License

Distributed under MIT License. See `LICENSE`.

---

<div align="center">
  <p>
    <strong>BITS AI Gateway</strong> Developed with ❤️ by <a href="https://bits.co.id"><strong>Banten IT Solutions</strong></a>
  </p>
</div>
