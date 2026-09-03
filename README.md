# Hi, I'm Amrit Raj 👋

**Backend / Platform Engineer | AI Infrastructure | Distributed & Real-Time Systems**

I build backend and AI systems where performance, correctness, reliability, and data isolation matter.  
I work primarily with TypeScript, Python, PostgreSQL, WebSockets, RAG, and distributed runtimes, and I contribute to open-source agent and actor infrastructure.

- 🔭 Currently working on distributed agent runtimes, real-time systems, and reliable AI execution.
- 📍 Based in India · Open to remote Backend, Platform & AI Engineering roles.
- 📫 [LinkedIn](https://www.linkedin.com/in/amrit-raj-8a30b8247) · [amritraj4work@gmail.com](mailto:amritraj4work@gmail.com)

---

## ⚙️ Engineering Focus

**Distributed Systems** · **AI Infrastructure** · **Real-Time Systems** · **PostgreSQL / pgvector** · **Performance & Reliability**

---

## 🏆 Featured Systems

### 01 — [Deterministic Real-Time Exchange Engine](https://github.com/iinaa-eimrit/Stock-Trading-Platform) | 🚀 [Live Demo](https://stock-trading-platform-one.vercel.app)
*TypeScript · Node.js · React · WebSockets · PostgreSQL · Docker · Prometheus · k6*

A deterministic real-time matching engine and financial exchange simulator built for low-latency trade execution and crash resilience.

- **Performance (37.5s → 29.8ms)**: Reduced 50K-order cancellation latency by **1,250×** by replacing naive array lookups with an in-memory SkipList price index and $O(1)$ order-ID map indexing.
- **Correctness**: Enforced strict fixed-point integer arithmetic (`PriceTicks` & `QuantityLots`) to eliminate IEEE-754 floating-point drift, verified across 100K-operation differential tests.
- **Reliability**: Implemented deterministic event journaling with periodic snapshot/replay recovery that withstands abrupt `SIGKILL` termination, settling idempotently into an ACID double-entry PostgreSQL ledger.

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

A multi-tenant RAG and validated tool-calling platform with PostgreSQL-enforced workspace isolation, pgvector retrieval, and streaming telemetry.

- **Database-Enforced Multi-Tenancy**: 0 unauthorized retrievals across 50 adversarial cross-tenant probes. Workspace isolation is enforced at the database layer inside a custom PostgreSQL `match_chunks` RPC (`WHERE dc.workspace_id = target_workspace_id`) across a shared HNSW index.
- **Grounded Responses & Refusal**: Retrieval thresholds and system-level rules trigger an explicit refusal when relevant workspace context is unavailable, coupled with inline source citations.
- **Validated Tool Execution & Controls**: Server validates tool arguments against strict schemas before executing side-effects (`save_task`, Discord webhooks); enforced SHA-256 `content_hash` constraints for idempotent document ingestion.

---

### 03 — Open Source Engineering

I actively contribute to distributed runtimes and agentic AI frameworks, focusing on runtime correctness, high-concurrency latency bottlenecks, and enterprise authentication.

#### **[aden-hive/hive](https://github.com/aden-hive/hive)** — *Multi-Agent Harness for Production AI*
- **✅ Merged Upstream ([#7356](https://github.com/aden-hive/hive/pull/7356))**: Added nearest-tool suggestions for unknown tool calls using Python's `difflib` matching to improve agent execution resilience.
- **In Review / Submitted**:
  - **LLM Self-Correction ([#7382](https://github.com/aden-hive/hive/pull/7382) / [#7392](https://github.com/aden-hive/hive/pull/7392))**: Captured structured Pydantic schema validation failures in the orchestrator and fed error reports back into the LLM context for real-time autonomous correction.
  - **Fail-Fast Validation ([#7395](https://github.com/aden-hive/hive/pull/7395))**: Added load-time validation for orchestrator `output_keys` to prevent silent graph execution failures.
  - **Runtime Reliability ([#7381](https://github.com/aden-hive/hive/pull/7381), [#7377](https://github.com/aden-hive/hive/pull/7377))**: Resolved Windows absolute path resolution bugs for MCP servers and added retry logic for atomic file operations.

#### **[rivet-dev/actors](https://github.com/rivet-dev/actors)** — *Stateful Distributed Primitive for AI Agents & Workloads*
- **In Review / Submitted**:
  - **$O(N) \to O(1)$ Request Lookup ([#5635](https://github.com/rivet-dev/actors/pull/5635), [Issue #5581](https://github.com/rivet-dev/actors/issues/5581))**: Profiled runner tunnel under high concurrency, isolated severe CPU bottleneck caused by linear array scanning in `requestToActor`, and refactored to $O(1)$ Map lookup.
  - **Enterprise OIDC/JWT Infrastructure ([#5572](https://github.com/rivet-dev/actors/pull/5572))**: Added external OIDC and JWT token verification inside `onAuth` lifecycle hooks with in-memory JWKS public-key caching.
  - **Inspector Protocol Fix ([#5596](https://github.com/rivet-dev/actors/pull/5596))**: Fixed missing WebSocket protocol headers required by actor inspector client connections.

---

## 🔬 Selected Research

### [Graph Database Cloud Benchmarking](https://github.com/iinaa-eimrit/Graph-Database-Cloud-Benchmarking)
*Python · Data Pipelines · Docker · Stanford SNAP Dataset · Cypher*

A reproducible empirical benchmark evaluating CognoDB Cloud against four major graph engines under identical workloads, standardized datasets, and resource constraints.

- **Controlled Workloads**: Subsampled the Stanford SNAP `soc-Pokec` network (20,000 nodes, 173,084 relationships) using BFS with fixed deterministic random seeds.
- **Parity & Resource Constraints**: Applied strict Docker resource limits (`--cpus=0.5 --memory=256m`) to self-hosted engines to match managed cloud free tiers.
- **Statistical Rigor**: Measured cold-start latency, warm-up iterations, and p50/p95 read latencies across multi-hop traversals and 40-client concurrent workloads.

---

## 📦 Additional Systems & Tooling

- **[Yield Visualizer](https://github.com/iinaa-eimrit/yield-visualizer)**: Real-time US Treasury yield curve and 10Y-2Y spread inversion tracker built with Python (FastAPI), WebSockets, and canvas charts.
- **[FinUI Design System](https://github.com/iinaa-eimrit/finUI)**: High-density, tree-shakeable React financial component library monorepo (`@amrit_16/core`, Storybook 8, Tailwind tokens, tsup).
- **[Financial Data & RBAC API](https://github.com/iinaa-eimrit/Finance-Data-Processing-and-Access-Control-Backend)** | 🚀 [Swagger Docs](https://finance-data-processing-and-access-7752.onrender.com/api/docs): Production NestJS & Prisma REST API enforcing role-based access control (Admin/Analyst/Viewer) with automated JWT validation.
- **[Pen-Pulse](https://github.com/iinaa-eimrit/Pen-Pulse)** | 🚀 [Live Demo](https://pen-pulse-roan.vercel.app/): Edge-deployed publishing backend on Cloudflare Workers with Prisma Accelerate connection pooling and shared Zod validation.
