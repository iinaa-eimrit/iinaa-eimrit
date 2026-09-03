# Hi, I'm Amrit Raj 👋

**Backend / Platform Engineer | AI Infrastructure | Distributed & Real-Time Systems**

I build production-oriented backend and AI systems with TypeScript, Python, PostgreSQL, WebSockets, RAG, tool calling, and distributed runtimes.  
I focus on correctness under failure, measured performance, database-enforced isolation, idempotency, observability, and reliable AI execution.

- 🔭 Currently profiling distributed agent runtimes, optimizing order matching throughput, and hardening RAG isolation boundaries.
- 🌱 Deep-diving into Rust-based actor runtimes, high-concurrency memory structures, and telemetry.
- 📫 Connect with me on [LinkedIn](https://www.linkedin.com/in/amrit-raj-8a30b8247) or reach out directly at **amritraj4work@gmail.com**.

---

## ⚙️ Engineering Focus

**Distributed & Real-Time Systems** · **AI Infrastructure & Agent Reliability** · **PostgreSQL / pgvector** · **WebSockets** · **Performance Engineering** · **Observability** · **Cloud & Serverless** · **Correctness Under Failure**

---

## 🏆 Featured Systems

### 01 — [Deterministic Real-Time Exchange Engine](https://github.com/iinaa-eimrit/Stock-Trading-Platform) | 🚀 [Live Demo](https://stock-trading-platform-one.vercel.app)
*TypeScript · Node.js · React · WebSockets · PostgreSQL · Docker · Prometheus · k6*

A deterministic real-time matching engine and financial exchange simulator built for low-latency trade execution and crash resilience.

- **50K-Order Cancellation Benchmark: 37.5s → 29.8ms (1,250× faster)**: Replaced naive linear array lookups with an in-memory SkipList price index and $O(1)$ order-ID map indexing.
- **Financial Invariant Correctness**: Replaced IEEE-754 floating-point numbers with custom fixed-point integer arithmetic (`PriceTicks` & `QuantityLots`), eliminating rounding drift across high-frequency fills.
- **Crash Recovery & Settlement**: Implemented deterministic event journaling with periodic snapshot/replay recovery that withstands abrupt `SIGKILL` termination, paired with an ACID double-entry settlement engine in PostgreSQL.
- **Multiplexed Streaming**: WebSocket architecture streaming live orderbook depth, trade feeds, and candlestick intervals without blocking the main event loop.

```text
Client ──► REST / WebSocket ──► Risk Check ──► Matching Engine (SkipList OB)
                                                     │
                                             Domain Events
                                             ┌───────┴───────┐
                                             ▼               ▼
                                       Event Journal     Settlement (PostgreSQL)
                                      (Snapshot/Replay) (ACID Double-Entry)
```

---

### 02 — [Multi-Workspace AI Document Assistant](https://github.com/iinaa-eimrit/Multi-Workspace-Document-Assistant-RAG-Tool-Calling-) | 🚀 [Live Demo](https://multi-workspace-document-assistant.vercel.app)
*Next.js 15 · Supabase (PostgreSQL / pgvector) · Gemini 2.5 Flash · SSE Streaming*

An enterprise-grade retrieval-augmented generation (RAG) and autonomous tool-calling platform designed for strict data isolation and reliability.

- **Database-Enforced Multi-Tenancy**: Workspace isolation is enforced at the database layer inside a custom PostgreSQL `match_chunks` RPC function (`WHERE dc.workspace_id = target_workspace_id`) across a shared HNSW index—guaranteeing zero cross-workspace data leakage.
- **Grounded Verification & Honest Refusal**: System prompts and similarity score cutoffs enforce honest "I don't know" refusal when context lacks evidence, coupled with inline source citations.
- **Autonomous Tool Execution**: Server validates LLM-proposed tool calls against strict schemas before executing side-effects (`save_task`, Discord webhook notifications), logging all inputs/outputs to a durable audit trail.
- **Production Controls**: SHA-256 `content_hash` unique constraints for idempotent document chunk ingestion, real-time SSE token streaming, and an interactive RAG debugger showing similarity scores.

```text
Document Ingestion ──► Chunking ──► gemini-embedding-2 (768d) ──► pgvector (HNSW)
                                                                       │
User Query ──► match_chunks RPC (Database-Level Isolation) ────────────┘
                     │
                     ▼
             Gemini 2.5 Flash ──► Schema-Validated Tool Calling ──► Side Effects (DB / Webhooks)
                     │
                     ▼
             SSE Streaming Output with Grounded Inline Citations
```

---

### 03 — Open Source Engineering

I actively contribute to open-source distributed runtimes and agentic AI frameworks, focusing on runtime correctness, high-concurrency latency bottlenecks, and enterprise authentication.

#### **[aden-hive/hive](https://github.com/aden-hive/hive)** — *Multi-Agent Harness for Production AI*
- **✅ Merged Upstream ([#7356](https://github.com/aden-hive/hive/pull/7356))**: Improved agent resilience by engineering a nearest-valid-tool suggestion mechanism using Levenshtein distance when an unknown tool call is received.
- **LLM Self-Correction Feedback Loop ([#7382](https://github.com/aden-hive/hive/pull/7382) / [#7392](https://github.com/aden-hive/hive/pull/7392))**: Engineered an orchestrator loop that captures Zod schema validation errors and feeds structured error reports back into the LLM context for real-time autonomous correction.
- **Fail-Fast Schema Validation ([#7395](https://github.com/aden-hive/hive/pull/7395))**: Enforced load-time validation for orchestrator `output_keys` to prevent silent graph execution failures.
- **Runtime Environment Hardening ([#7381](https://github.com/aden-hive/hive/pull/7381), [#7377](https://github.com/aden-hive/hive/pull/7377))**: Resolved Windows absolute path resolution bugs for MCP servers and added exponential retry backoff for atomic file operations.

#### **[rivet-dev/actors](https://github.com/rivet-dev/actors)** — *Stateful Distributed Primitive for AI Agents & Workloads*
- **High-Concurrency $O(1)$ Optimization ([#5635](https://github.com/rivet-dev/actors/pull/5635), [Issue #5581](https://github.com/rivet-dev/actors/issues/5581))**: Profiled runner tunnel under high load, isolated severe CPU bottleneck caused by linear array scanning in `requestToActor`, and refactored to $O(1)$ Map lookup.
- **Enterprise OIDC/JWT Infrastructure ([#5572](https://github.com/rivet-dev/actors/pull/5572))**: Added external OIDC and JWT token verification inside `onAuth` lifecycle hooks with in-memory JWKS public-key caching.
- **Inspector Protocol Fix ([#5596](https://github.com/rivet-dev/actors/pull/5596))**: Fixed missing WebSocket protocol headers required by actor inspector client connections.

---

## 🔬 Selected Research

### [Graph Database Cloud Benchmarking](https://github.com/iinaa-eimrit/Graph-Database-Cloud-Benchmarking)
*Python · Data Pipelines · Docker · Stanford SNAP Dataset · Cypher · Neo4j AuraDB · Memgraph · FalkorDB · ArangoDB*

A reproducible empirical benchmark evaluating CognoDB Cloud against four major graph engines under identical workloads, standardized datasets, and resource constraints.

- **Controlled Workload Design**: Subsampled the Stanford SNAP `soc-Pokec` social network (20,000 nodes, 173,084 directed relationships) using BFS with fixed deterministic random seeds.
- **Fairness & Resource Constraints**: Applied strict Docker resource constraints (`--cpus=0.5 --memory=256m`) to self-hosted engines to match managed cloud free tiers; documented network latency differences transparently.
- **Statistical Rigor**: Measured cold-start overhead, warm-up iterations, and p50/p95 read latencies across 1-hop, 2-hop, and 3-hop traversals alongside 40-client concurrent read/write throughput.

---

## 📦 Additional Systems & Tooling

- **[Yield Visualizer](https://github.com/iinaa-eimrit/yield-visualizer)**: Full-stack real-time US Treasury yield curve and 10Y-2Y spread inversion tracker built with Python (FastAPI), WebSockets, and canvas charts.
- **[FinUI Design System](https://github.com/iinaa-eimrit/finUI)**: High-density, tree-shakeable React financial component library monorepo (`@amrit_16/core`, Storybook 8, Tailwind tokens, tsup).
- **[Financial Data & RBAC API](https://github.com/iinaa-eimrit/Finance-Data-Processing-and-Access-Control-Backend)** | 🚀 [Swagger Docs](https://finance-data-processing-and-access-7752.onrender.com/api/docs): Production NestJS & Prisma RESTful API enforcing role-based access control (Admin/Analyst/Viewer) with automated JWT validation and financial records processing.
- **[Pen-Pulse](https://github.com/iinaa-eimrit/Pen-Pulse)** | 🚀 [Live Demo](https://pen-pulse-roan.vercel.app/): Edge-deployed social publishing backend on Cloudflare Workers with Prisma Accelerate connection pooling and shared Zod validation.
