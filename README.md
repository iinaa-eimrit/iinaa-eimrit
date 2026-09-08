# Hi, I'm Amrit Raj 👋

### Backend / Systems Engineer
*Interested in systems reliability, performance engineering, and AI-enabled applications.*

I build backend systems where correctness, data isolation, and crash resilience matter. I enjoy working on the layer beneath the application—debugging latency bottlenecks, resolving concurrency races, and building predictable state machines.

- 🎯 **Target Roles**: Backend Engineer, Platform Engineer, AI/LLM Backend Engineer
- 🛠️ **Core Stack**: TypeScript · Python · PostgreSQL · Distributed Systems · Real-Time Systems · LLM Systems
- 📍 India · Open to Remote opportunities worldwide
- 📫 [LinkedIn](https://www.linkedin.com/in/amrit-raj-8a30b8247) · [amritraj4work@gmail.com](mailto:amritraj4work@gmail.com)

---

## 💭 How I Approach Systems

- **Profile before adding infrastructure**: Benchmark single-node in-memory structures and relational transactions before reaching for distributed brokers or caching layers.
- **Hands-on with unfamiliar codebases**: Profile bottlenecks, write reproducible tests, and contribute targeted upstream fixes rather than treating dependencies as black boxes.

---

## 🛠️ Open Source Engineering

I contribute targeted fixes, error handling, and performance improvements to upstream agent harnesses and distributed actor runtimes:

### [aden-hive/hive](https://github.com/aden-hive/hive) — Multi-Agent Harness
Targeted contributions around orchestrator validation, retry feedback, and platform reliability:
- **✅ Merged Upstream**:
  - **Fuzzy Tool Suggestions ([#7356](https://github.com/aden-hive/hive/pull/7356))**: Implemented closest-match suggestions for unknown tool invocations using Python's `difflib` to make autonomous agent tool calling resilient to typos.
- **Active Submissions / In Review**:
  - **Validation-Error Retry ([#7392](https://github.com/aden-hive/hive/pull/7392))**: Added structured validation-error feedback to the orchestrator loop to retry model outputs when schema validation fails.
  - **Windows Path & File Reliability ([#7381](https://github.com/aden-hive/hive/pull/7381), [#7377](https://github.com/aden-hive/hive/pull/7377))**: Resolved Windows path normalization issues for MCP servers and added retries for atomic file writes on `PermissionError`.
  - **Pipeline Timeout Handling ([#7430](https://github.com/aden-hive/hive/pull/7430))**: Added timeout bounds across sequential node pipelines.

### [rivet-dev/actors](https://github.com/rivet-dev/actors) — Stateful Distributed Runtime
Contributions around runner performance, authentication hooks, and protocol handling:
- **Active Submissions / In Review**:
  - **$O(N) \to O(1)$ Request Lookup ([#5635](https://github.com/rivet-dev/actors/pull/5635), [Issue #5581](https://github.com/rivet-dev/actors/issues/5581))**: Profiled runner tunnel under high concurrency, identified event-loop blocking caused by linear array scanning in `requestToActor`, and refactored the lookup to an $O(1)$ Map.
  - **External JWT/OIDC Verification ([#5572](https://github.com/rivet-dev/actors/pull/5572))**: Added JWT verification utility with in-memory JWKS caching for `onAuth` lifecycle hooks.
  - **Inspector Protocol Fix ([#5596](https://github.com/rivet-dev/actors/pull/5596))**: Fixed missing WebSocket protocol headers for actor inspector client connections.

---

## ⚙️ Selected Systems Projects

### [Deterministic Real-Time Exchange Simulator](https://github.com/iinaa-eimrit/Stock-Trading-Platform) | [Live Demo](https://stock-trading-platform-one.vercel.app)
*TypeScript · Node.js · React · WebSockets · PostgreSQL · Docker*

A deterministic exchange simulator exploring orderbook data structures, fixed-point arithmetic, durable event journaling, crash recovery, and transactional settlement.
- **Measured SkipList Speedup**: A controlled 50K-resting-order benchmark reduced cancellation time from 37.5s to 29.8ms by replacing linear order scanning with a SkipList price index and an $O(1)$ order-ID lookup map.
- **Domain Invariants**: Implemented strict fixed-point integer arithmetic (`PriceTicks` & `QuantityLots`) to eliminate IEEE-754 floating-point drift, verified across 100K-operation differential tests.
- **Crash Recovery & Reconciliation**: Implemented durable event journaling with snapshot/replay recovery that survives abrupt `SIGKILL` termination, settling idempotently into an ACID double-entry PostgreSQL ledger with automated 3-way balance reconciliation.

---

## 🤖 AI Prototypes

### [Multi-Workspace Document Assistant](https://github.com/iinaa-eimrit/Multi-Workspace-Document-Assistant-RAG-Tool-Calling-) | [Live Demo](https://multi-workspace-document-assistant.vercel.app)
*Next.js 15 · PostgreSQL / pgvector (Supabase) · Gemini 2.5 Flash · SSE Streaming*

A multi-tenant RAG application with database-enforced workspace isolation, validated tool calling, source citations, streaming responses, and ingestion idempotency.
- **Database-Enforced Multi-Tenancy**: Workspace isolation and caller authorization are enforced at the database layer inside a PostgreSQL `match_chunks` RPC, verifying `auth.uid()` membership before executing vector retrieval across a shared HNSW index.
- **Grounded Responses & Refusal**: Retrieval thresholds and system-level rules trigger explicit refusals when relevant workspace context is unavailable, coupled with inline source citations.
- **Validated Tool Execution & Idempotency**: Schema-validated tool execution for side-effects; enforced SHA-256 `content_hash` constraints to guarantee idempotent document ingestion.

### [MediCo — Medical Workflow AI Prototype](https://github.com/iinaa-eimrit/AI-Medical-Consultation-Co-pilot-Voice-LLM-)
*React 18 · Vite · TypeScript · Tailwind CSS · Zustand · Zod · Google Gemini*

A technical prototype exploring audio transcription UX, structured clinical entity extraction, schema validation, and LLM-assisted workflow orchestration. *(Not intended for clinical use.)*
- Demonstrates browser-based audio capture, structured extraction into clinical schemas (diagnoses, medications, follow-ups), and a validation-and-retry loop routing Zod errors back to the model for real-time schema correction.

---

## 🔬 Research & Benchmarking

### [Graph Database Cloud Benchmarking](https://github.com/iinaa-eimrit/Graph-Database-Cloud-Benchmarking)
*Python · Docker · Cypher · AQL · Stanford SNAP Dataset*

A reproducible benchmark evaluating graph database engines (CognoDB Cloud, Neo4j AuraDB, Memgraph Cloud, ArangoDB, FalkorDB) under controlled workloads, standardized datasets, and explicit fairness/measurement caveats.
- Evaluates data ingestion, 1/2/3-hop traversals, aggregations, and concurrent read/write workloads with p50/p95 latency metrics.
- Explicitly documents architectural trade-offs, network-vs-local latency deltas, and resource constraint limitations across tiers.

---

## 📦 Other Projects & Earlier Work

- **[Yield Visualizer](https://github.com/iinaa-eimrit/yield-visualizer)**: Full-stack real-time US Treasury yield curve and 10Y-2Y spread inversion tracker built with Python (FastAPI), WebSockets, and canvas charts.
- **[FinUI Design System](https://github.com/iinaa-eimrit/finUI)**: High-density React component library monorepo (`@amrit_16/core`, Storybook 8, Tailwind tokens, tsup) built for financial interfaces.
- **[Financial Data & RBAC API](https://github.com/iinaa-eimrit/Finance-Data-Processing-and-Access-Control-Backend)** | [Swagger Docs](https://finance-data-processing-and-access-7752.onrender.com/api/docs): Backend REST API demonstrating role-based access control (Admin/Analyst/Viewer), automated JWT validation, and financial record processing built with NestJS and Prisma.
- **[Pen-Pulse](https://github.com/iinaa-eimrit/Pen-Pulse)** | [Live Demo](https://pen-pulse-roan.vercel.app/): Earlier backend project exploring Cloudflare Workers, Prisma Accelerate connection pooling, and shared Zod validation.

---

## 🎯 Engineering Interests

Distributed Systems · Backend Architecture · LLM Systems · Real-Time Systems · Reliability & Fault Tolerance · Performance Engineering
