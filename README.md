# Herman Hoffman · Hoffman Alternative

Full-cycle engineer. I design backend and infrastructure systems, build the interfaces on top of them, and run them on Linux servers I harden myself.

Every project below is public, MIT-licensed and has CI that runs on each push. Where a README quotes a number, it comes from a test, a benchmark in the repo, or the CI job summary.

## What I take on

- Backend services and APIs in Go and Python: queues, rate limiting, auth, consistency under failure.
- Kubernetes and infrastructure as code: operators, Helm, Argo CD, Terraform.
- Self-hosted AI on CPU-only servers: local LLMs, retrieval pipelines with measured quality.
- Telegram bots and passwordless login flows.
- Web interfaces with a HUD / terminal look that still pass accessibility and performance checks.
- Server hardening, monitoring and alerting for small teams without a dedicated ops person.

## Selected work

### Distributed systems

| Project | What it shows | CI |
|---|---|---|
| [raft-kv](https://github.com/HOFFMAN-ALTERNATIVE/raft-kv) | Raft written from scratch in Go behind a replicated KV store. Pre-Vote, CheckQuorum, ReadIndex reads, snapshots, exactly-once sessions. Linearizability checked with porcupine under partitions. | ![ci](https://github.com/HOFFMAN-ALTERNATIVE/raft-kv/actions/workflows/ci.yml/badge.svg) |
| [distributed-rate-limiter](https://github.com/HOFFMAN-ALTERNATIVE/distributed-rate-limiter) | Token bucket and sliding-window log in Go. Each Redis decision is one Lua script, so replicas cannot race. Exactness tested across replicas. | ![ci](https://github.com/HOFFMAN-ALTERNATIVE/distributed-rate-limiter/actions/workflows/ci.yml/badge.svg) |
| [event-driven-microservices](https://github.com/HOFFMAN-ALTERNATIVE/event-driven-microservices) | Four Go services coordinating an order saga over NATS JetStream: transactional outbox, idempotent consumers, compensation, DLQ with replay, one trace across async hops. | ![ci](https://github.com/HOFFMAN-ALTERNATIVE/event-driven-microservices/actions/workflows/ci.yml/badge.svg) |
| [crdt-collab](https://github.com/HOFFMAN-ALTERNATIVE/crdt-collab) · [demo](https://hoffman-alternative.github.io/crdt-collab/) | Collaborative text and whiteboard on a CRDT written from scratch (RGA + LWW). Offline merge, presence, convergence checked with fast-check. | ![ci](https://github.com/HOFFMAN-ALTERNATIVE/crdt-collab/actions/workflows/ci.yml/badge.svg) |

### Platform and infrastructure

| Project | What it shows | CI |
|---|---|---|
| [k8s-operator](https://github.com/HOFFMAN-ALTERNATIVE/k8s-operator) | Tenant operator on controller-runtime v0.25: isolated namespaces with quota, NetworkPolicies, RBAC and Pod Security via server-side apply, drift correction, finalizers. envtest plus kind e2e. | ![ci](https://github.com/HOFFMAN-ALTERNATIVE/k8s-operator/actions/workflows/ci.yml/badge.svg) |
| [gitops-helm-demo](https://github.com/HOFFMAN-ALTERNATIVE/gitops-helm-demo) | Hardened Helm chart promoted dev, staging, prod by an Argo CD app-of-apps. CI syncs it on kind and runs a self-heal drill. | ![ci](https://github.com/HOFFMAN-ALTERNATIVE/gitops-helm-demo/actions/workflows/ci.yml/badge.svg) |
| [terraform-modules](https://github.com/HOFFMAN-ALTERNATIVE/terraform-modules) | VPC, S3 and naming modules with secure defaults. 26 `terraform test` runs on mocked providers, so CI needs no cloud credentials. | ![ci](https://github.com/HOFFMAN-ALTERNATIVE/terraform-modules/actions/workflows/ci.yml/badge.svg) |
| [ebpf-netmon](https://github.com/HOFFMAN-ALTERNATIVE/ebpf-netmon) | cgroup_skb programs count bytes per IPv4/IPv6 flow in the kernel; a Go agent exports top talkers to Prometheus. CI loads the program into a real kernel. | ![ci](https://github.com/HOFFMAN-ALTERNATIVE/ebpf-netmon/actions/workflows/ci.yml/badge.svg) |
| [observability-stack](https://github.com/HOFFMAN-ALTERNATIVE/observability-stack) | Prometheus, Alertmanager to Telegram, provisioned Grafana, Loki and Alloy in one compose file. Alert rules are unit-tested. | ![ci](https://github.com/HOFFMAN-ALTERNATIVE/observability-stack/actions/workflows/ci.yml/badge.svg) |
| [devops-scripts](https://github.com/HOFFMAN-ALTERNATIVE/devops-scripts) | Bash for server bootstrap, SSH hardening, restic backups, TLS and uptime checks. ShellCheck-clean, bats-tested. | ![ci](https://github.com/HOFFMAN-ALTERNATIVE/devops-scripts/actions/workflows/ci.yml/badge.svg) |
| [server-hardening-kit](https://github.com/HOFFMAN-ALTERNATIVE/server-hardening-kit) | nginx, Cloudflare, backup, systemd timer and health-check templates for a single VPS. | ![ci](https://github.com/HOFFMAN-ALTERNATIVE/server-hardening-kit/actions/workflows/shellcheck.yml/badge.svg) |

### Security

| Project | What it shows | CI |
|---|---|---|
| [zero-trust-gateway](https://github.com/HOFFMAN-ALTERNATIVE/zero-trust-gateway) | Identity-aware reverse proxy in Go: OIDC with PKCE, JWKS rotation, deny-by-default policy, mTLS 1.3 to upstreams, JSON audit log. JWT and OIDC code use only the standard library. | ![ci](https://github.com/HOFFMAN-ALTERNATIVE/zero-trust-gateway/actions/workflows/ci.yml/badge.svg) |
| [wasm-plugin-runtime](https://github.com/HOFFMAN-ALTERNATIVE/wasm-plugin-runtime) | Runs untrusted WebAssembly plugins in-process with per-call fuel, memory, wall-clock and capability limits. About 21 µs per call with a fresh instance each time. | ![ci](https://github.com/HOFFMAN-ALTERNATIVE/wasm-plugin-runtime/actions/workflows/ci.yml/badge.svg) |
| [telegram-otp-auth](https://github.com/HOFFMAN-ALTERNATIVE/telegram-otp-auth) | Website login with one-time codes sent by a Telegram bot. Codes are HMAC-hashed and single-use, with attempt limits and lockout. | ![ci](https://github.com/HOFFMAN-ALTERNATIVE/telegram-otp-auth/actions/workflows/ci.yml/badge.svg) |

### Search and self-hosted AI

| Project | What it shows | CI |
|---|---|---|
| [hnsw-vector-search](https://github.com/HOFFMAN-ALTERNATIVE/hnsw-vector-search) | HNSW index in Rust from the paper, no ANN libraries. 0.976 recall@10 at 11k queries/s on one thread (50k x 128-d). Recall is gated in CI. | ![ci](https://github.com/HOFFMAN-ALTERNATIVE/hnsw-vector-search/actions/workflows/ci.yml/badge.svg) |
| [cpu-rag-pipeline](https://github.com/HOFFMAN-ALTERNATIVE/cpu-rag-pipeline) | RAG on a CPU: BM25 plus dense retrieval fused with RRF, cited answers. hit@k, MRR and nDCG are gated in CI; NumPy is the only runtime dependency. | ![ci](https://github.com/HOFFMAN-ALTERNATIVE/cpu-rag-pipeline/actions/workflows/ci.yml/badge.svg) |
| [self-hosted-ai-stack](https://github.com/HOFFMAN-ALTERNATIVE/self-hosted-ai-stack) | Ollama and Open WebUI behind a FastAPI gateway with API keys, rate limits and streaming. CI runs end-to-end tests against a real model. | ![ci](https://github.com/HOFFMAN-ALTERNATIVE/self-hosted-ai-stack/actions/workflows/ci.yml/badge.svg) |

### Interfaces, templates and tooling

| Project | What it shows | CI |
|---|---|---|
| [webgpu-hud](https://github.com/HOFFMAN-ALTERNATIVE/webgpu-hud) · [demo](https://hoffman-alternative.github.io/webgpu-hud/) | Tactical HUD on three.js WebGPURenderer with automatic WebGL 2 fallback. Respects reduced-motion settings. | ![ci](https://github.com/HOFFMAN-ALTERNATIVE/webgpu-hud/actions/workflows/ci.yml/badge.svg) |
| [cyber-ui-kit](https://github.com/HOFFMAN-ALTERNATIVE/cyber-ui-kit) · [demo](https://hoffman-alternative.github.io/cyber-ui-kit/) | HUD-style components in plain CSS and dependency-free JS. | ![ci](https://github.com/HOFFMAN-ALTERNATIVE/cyber-ui-kit/actions/workflows/ci.yml/badge.svg) |
| [hoffman-eye](https://github.com/HOFFMAN-ALTERNATIVE/hoffman-eye) · [demo](https://hoffman-alternative.github.io/hoffman-eye/) | Terminal-style portal prototype and its case study. | |
| [fastapi-production-template](https://github.com/HOFFMAN-ALTERNATIVE/fastapi-production-template) | FastAPI, async SQLAlchemy 2, Alembic, Postgres, Redis, JWT with Argon2, structured logs, Prometheus. mypy strict, coverage gate at 85%. | ![ci](https://github.com/HOFFMAN-ALTERNATIVE/fastapi-production-template/actions/workflows/ci.yml/badge.svg) |
| [telegram-bot-starter](https://github.com/HOFFMAN-ALTERNATIVE/telegram-bot-starter) | aiogram 3 bot template with typed config, inline menus and an optional local LLM. | ![ci](https://github.com/HOFFMAN-ALTERNATIVE/telegram-bot-starter/actions/workflows/ci.yml/badge.svg) |
| [logscope](https://github.com/HOFFMAN-ALTERNATIVE/logscope) | Rust CLI that tails and aggregates JSON, logfmt and nginx logs with exact latency percentiles. | ![ci](https://github.com/HOFFMAN-ALTERNATIVE/logscope/actions/workflows/ci.yml/badge.svg) |
| [universal-testing-toolkit](https://github.com/HOFFMAN-ALTERNATIVE/universal-testing-toolkit) | QA suite you point at any site: Playwright on five browser/device profiles, API contracts, axe, visual regression, Lighthouse budgets, k6, OWASP ZAP. | ![ci](https://github.com/HOFFMAN-ALTERNATIVE/universal-testing-toolkit/actions/workflows/ci.yml/badge.svg) |

## Stack

Go, Rust, Python, TypeScript. PostgreSQL, Redis, NATS JetStream. Docker, Kubernetes, Helm, Argo CD, Terraform, eBPF. Prometheus, Grafana, Loki, OpenTelemetry. nginx, Caddy, Cloudflare. FastAPI, aiogram, three.js, Playwright. Ollama for local models.

## How I work

I write down the decisions that are expensive to reverse, keep secrets out of repos, run containers as non-root, and treat a red CI run as unfinished work. If a trade-off was made, the README says so.

## Contact

Email: [blackdmn666@gmail.com](mailto:blackdmn666@gmail.com). Open to freelance and contract work. Send a short description of the problem and I will reply with a plan, a timeline and a price.
