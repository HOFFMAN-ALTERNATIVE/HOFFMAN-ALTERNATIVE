# Herman Hoffman · Hoffman Alternative

**I build distinctive web interfaces, Telegram bots and self-hosted AI — and run them on hardened Linux servers.**

Cyberpunk / HUD-style frontends that actually work in production, bots that automate real workflows,
local LLMs running on plain CPUs (no GPU, no cloud bills), and infrastructure that is locked down behind Cloudflare.

## 🛠 Services

- **Web interfaces** — landing pages, dashboards and portals with cyberpunk / HUD / terminal aesthetics, animations, responsive layout
- **Telegram bots** — aiogram 3, inline menus, notifications, integrations, admin-friendly control panels
- **Self-hosted local AI** — Ollama / quantized LLMs on CPU-only VPS, chat assistants for sites and bots
- **Linux / DevOps** — server hardening, nginx, Docker, systemd automation, backups, monitoring and alerts
- **Cloudflare** — DNS, proxying, WAF and rate limiting, real-IP configuration

## ⚙️ Tech stack

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Go](https://img.shields.io/badge/Go-00ADD8?style=for-the-badge&logo=go&logoColor=white)
![Rust](https://img.shields.io/badge/Rust-000000?style=for-the-badge&logo=rust&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white)
![Three.js](https://img.shields.io/badge/Three.js_WebGPU-000000?style=for-the-badge&logo=threedotjs&logoColor=white)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)
![Telegram](https://img.shields.io/badge/aiogram-26A5E4?style=for-the-badge&logo=telegram&logoColor=white)
![Ollama](https://img.shields.io/badge/Ollama-000000?style=for-the-badge&logo=ollama&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![nginx](https://img.shields.io/badge/nginx-009639?style=for-the-badge&logo=nginx&logoColor=white)
![Cloudflare](https://img.shields.io/badge/Cloudflare-F38020?style=for-the-badge&logo=cloudflare&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=for-the-badge&logo=redis&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white)
![Prometheus](https://img.shields.io/badge/Prometheus-E6522C?style=for-the-badge&logo=prometheus&logoColor=white)
![Grafana](https://img.shields.io/badge/Grafana-F46800?style=for-the-badge&logo=grafana&logoColor=white)
![Playwright](https://img.shields.io/badge/Playwright-2EAD33?style=for-the-badge&logo=playwright&logoColor=white)
![Terraform](https://img.shields.io/badge/Terraform-7B42BC?style=for-the-badge&logo=terraform&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=githubactions&logoColor=white)

## 🚀 Featured projects

| Project | What it is | |
|---|---|---|
| [**cpu-rag-pipeline**](https://github.com/HOFFMAN-ALTERNATIVE/cpu-rag-pipeline) | Local CPU-only RAG: heading-aware chunking, deterministic hashing + pluggable embeddings, float32/int8 vector store, BM25 + dense hybrid via RRF, cited answers — retrieval metrics (hit@k, MRR, nDCG) gated in CI, mypy strict, 99% coverage | ![ci](https://github.com/HOFFMAN-ALTERNATIVE/cpu-rag-pipeline/actions/workflows/ci.yml/badge.svg) |
| [**ebpf-netmon**](https://github.com/HOFFMAN-ALTERNATIVE/ebpf-netmon) | eBPF network monitor in Go (cilium/ebpf): cgroup_skb per-flow IPv4/IPv6 accounting in an LRU map, top-talkers CLI, bounded-cardinality Prometheus exporter — verifier + attach tested on a real kernel in CI | ![ci](https://github.com/HOFFMAN-ALTERNATIVE/ebpf-netmon/actions/workflows/ci.yml/badge.svg) |
| [**terraform-modules**](https://github.com/HOFFMAN-ALTERNATIVE/terraform-modules) | Reusable Terraform modules (naming/tagging, multi-AZ VPC with NAT modes + flow logs, TLS-only encrypted S3) with secure defaults — 26 `terraform test` runs on mocked providers, tflint, Terraform 1.9 + 1.12 matrix | ![ci](https://github.com/HOFFMAN-ALTERNATIVE/terraform-modules/actions/workflows/ci.yml/badge.svg) |
| [**webgpu-hud**](https://github.com/HOFFMAN-ALTERNATIVE/webgpu-hud) · [▶ live demo](https://hoffman-alternative.github.io/webgpu-hud/) | Volumetric cyberpunk tactical HUD on three.js WebGPURenderer + TSL node materials with automatic WebGL 2 fallback: holographic radar, GPU particles, bloom, simulated telemetry, reduced-motion aware | ![ci](https://github.com/HOFFMAN-ALTERNATIVE/webgpu-hud/actions/workflows/ci.yml/badge.svg) |
| [**zero-trust-gateway**](https://github.com/HOFFMAN-ALTERNATIVE/zero-trust-gateway) | BeyondCorp-style identity-aware proxy in Go: OIDC/JWT with JWKS rotation, PKCE login, deny-by-default YAML policy, mTLS 1.3 upstreams, signed sessions, JSON audit log, threat model | ![ci](https://github.com/HOFFMAN-ALTERNATIVE/zero-trust-gateway/actions/workflows/ci.yml/badge.svg) |
| [**crdt-collab**](https://github.com/HOFFMAN-ALTERNATIVE/crdt-collab) · [▶ live demo](https://hoffman-alternative.github.io/crdt-collab/) | Realtime collaborative text + whiteboard on a from-scratch CRDT (RGA + LWW): WebSocket sync server, presence, offline merge, fast-check convergence proofs | ![ci](https://github.com/HOFFMAN-ALTERNATIVE/crdt-collab/actions/workflows/ci.yml/badge.svg) |
| [**event-driven-microservices**](https://github.com/HOFFMAN-ALTERNATIVE/event-driven-microservices) | Go microservices over NATS JetStream: transactional outbox, idempotent consumers, saga with compensation, DLQ + replay, one OpenTelemetry trace across async hops | ![ci](https://github.com/HOFFMAN-ALTERNATIVE/event-driven-microservices/actions/workflows/ci.yml/badge.svg) |
| [**distributed-rate-limiter**](https://github.com/HOFFMAN-ALTERNATIVE/distributed-rate-limiter) | Go rate limiter library + HTTP service: token bucket & sliding-window log, atomic Redis Lua scripts, net/http middleware, Prometheus — exactness tested across replicas | ![ci](https://github.com/HOFFMAN-ALTERNATIVE/distributed-rate-limiter/actions/workflows/ci.yml/badge.svg) |
| [**logscope**](https://github.com/HOFFMAN-ALTERNATIVE/logscope) | Rust CLI to tail, filter and aggregate JSON / logfmt / nginx logs: query language, top-N, exact p50–p99 latency, follow mode | ![ci](https://github.com/HOFFMAN-ALTERNATIVE/logscope/actions/workflows/ci.yml/badge.svg) |
| [**universal-testing-toolkit**](https://github.com/HOFFMAN-ALTERNATIVE/universal-testing-toolkit) | Point-and-shoot QA suite for any site: Playwright E2E on 5 browsers/devices, API contracts, axe a11y, visual regression, Lighthouse CI, k6 load, OWASP ZAP | ![ci](https://github.com/HOFFMAN-ALTERNATIVE/universal-testing-toolkit/actions/workflows/ci.yml/badge.svg) |
| [**self-hosted-ai-stack**](https://github.com/HOFFMAN-ALTERNATIVE/self-hosted-ai-stack) | Private ChatGPT on a CPU-only VPS: Ollama + Open WebUI + hardened API gateway (keys, rate limits, streaming) + Caddy auto-TLS | ![ci](https://github.com/HOFFMAN-ALTERNATIVE/self-hosted-ai-stack/actions/workflows/ci.yml/badge.svg) |
| [**fastapi-production-template**](https://github.com/HOFFMAN-ALTERNATIVE/fastapi-production-template) | FastAPI + async SQLAlchemy 2 + Alembic + Postgres + Redis, JWT, structlog, Prometheus, mypy strict, ≥85% coverage | ![ci](https://github.com/HOFFMAN-ALTERNATIVE/fastapi-production-template/actions/workflows/ci.yml/badge.svg) |
| [**telegram-otp-auth**](https://github.com/HOFFMAN-ALTERNATIVE/telegram-otp-auth) | Passwordless website login via Telegram one-time codes — HMAC-hashed, single-use, lockout, rate limits, threat model | ![ci](https://github.com/HOFFMAN-ALTERNATIVE/telegram-otp-auth/actions/workflows/ci.yml/badge.svg) |
| [**observability-stack**](https://github.com/HOFFMAN-ALTERNATIVE/observability-stack) | Prometheus, Alertmanager → Telegram, provisioned Grafana, Loki + Alloy, node-exporter, cAdvisor — rules unit-tested | ![ci](https://github.com/HOFFMAN-ALTERNATIVE/observability-stack/actions/workflows/ci.yml/badge.svg) |
| [**cyber-ui-kit**](https://github.com/HOFFMAN-ALTERNATIVE/cyber-ui-kit) · [▶ live demo](https://hoffman-alternative.github.io/cyber-ui-kit/) | Cyberpunk / HUD components in plain CSS + 0-dependency JS: glitch, CRT power-off, nixie countdown, HUD panels | ![ci](https://github.com/HOFFMAN-ALTERNATIVE/cyber-ui-kit/actions/workflows/ci.yml/badge.svg) |
| [**hoffman-eye**](https://github.com/HOFFMAN-ALTERNATIVE/hoffman-eye) · [▶ live demo](https://hoffman-alternative.github.io/hoffman-eye/) | Cyberpunk HUD web interface prototype + case study of a terminal-style portal | |
| [**devops-scripts**](https://github.com/HOFFMAN-ALTERNATIVE/devops-scripts) | Bash toolbox: server bootstrap & SSH hardening, Docker, restic S3 backups, TLS/uptime checks — ShellCheck + bats | ![ci](https://github.com/HOFFMAN-ALTERNATIVE/devops-scripts/actions/workflows/ci.yml/badge.svg) |
| [**server-hardening-kit**](https://github.com/HOFFMAN-ALTERNATIVE/server-hardening-kit) | nginx, Cloudflare, backups, systemd timers, Docker and health-check templates | ![ci](https://github.com/HOFFMAN-ALTERNATIVE/server-hardening-kit/actions/workflows/shellcheck.yml/badge.svg) |
| [**telegram-bot-starter**](https://github.com/HOFFMAN-ALTERNATIVE/telegram-bot-starter) | Modern aiogram 3 bot template with typed config, inline menus, optional local LLM | ![ci](https://github.com/HOFFMAN-ALTERNATIVE/telegram-bot-starter/actions/workflows/ci.yml/badge.svg) |

## 📬 Contact

[![Email](https://img.shields.io/badge/Email-blackdmn666%40gmail.com-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:blackdmn666@gmail.com)

Open for freelance projects. Write to discuss your task.
