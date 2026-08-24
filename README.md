# Hi, I'm Amrit Raj 👋

**Backend-Heavy Full-Stack Engineer | Real-Time Systems & Distributed Data**

I engineer scalable backend systems and data-intensive full-stack platforms. I specialize in TypeScript, low-latency data streaming (WebSockets), database optimization (PostgreSQL/pgvector), and deploying serverless architectures to the edge.

- Currently architecting real-time streaming platforms and serverless APIs (Cloudflare Workers, Prisma Accelerate, Monorepos).
- Profiling open-source frameworks to resolve CPU bottlenecks and integrating enterprise-grade authentication (OIDC/JWT) at the infrastructure layer.
- Connect with me on [LinkedIn](https://www.linkedin.com/in/amrit-raj-8a30b8247) or reach out at amritraj4work@gmail.com.

---

### Projects

**1. [Stock Trading Platform](https://github.com/iinaa-eimrit/Stock-Trading-Platform)** | **[Live Demo](https://stock-trading-platform-one.vercel.app)**
A low-latency trading engine built for concurrent order execution and live portfolio management.
**Tech Stack:** TypeScript, Node.js, React, WebSockets, PostgreSQL.
**Engineering Feat:** Designed a multiplexed WebSocket streaming architecture that pushes real-time market tick data to the client without blocking the main UI thread. Implemented strict concurrency controls to eliminate race conditions in financial state management.

**2. [Multi-Workspace Document Assistant](https://github.com/iinaa-eimrit/Multi-Workspace-Document-Assistant-RAG-Tool-Calling-)** | **[Live Demo](https://multi-workspace-document-assistant.vercel.app)**
An enterprise-grade Retrieval-Augmented Generation (RAG) pipeline with autonomous tool calling.
**Tech Stack:** Node.js, Next.js, pgvector, Gemini 2.5 Flash.
**Engineering Feat:** Engineered a robust prompt-chaining loop, complex data chunking, and vector similarity search that effectively mitigates LLM hallucinations during multi-workspace queries.

**3. [Pen Pulse API](https://github.com/iinaa-eimrit/Pen-Pulse)** | **[Live Demo](https://pen-pulse-roan.vercel.app/)**
A highly scalable, serverless backend for a social journalism platform.
**Tech Stack:** Cloudflare Workers, TypeScript, Prisma Accelerate, Zod.
**Engineering Feat:** Deployed entirely to the edge with a strict monorepo architecture. Solved edge-to-database connection bottlenecks using Prisma Accelerate and enforced end-to-end type safety with shared Zod validation schemas.

**4. [Space Shooter Game Engine](https://github.com/iinaa-eimrit/Space-Shooter-Game-Engine)**
A custom, high-performance 2D game engine built entirely from scratch.
**Tech Stack:** C++.
**Engineering Feat:** Built to demonstrate strict system-level programming. Optimized memory management and rendering loops to maintain a consistent high frame rate under heavy sprite loads.

**5. [Graph Database Cloud Benchmarking](https://github.com/iinaa-eimrit/Graph-Database-Cloud-Benchmarking)**
A comprehensive data engineering benchmark suite comparing cloud graph databases.
**Tech Stack:** Python, Data Pipelines, Graph Databases.
**Engineering Feat:** Rigorously compared managed graph database cloud platforms using standardized, heavy-load datasets and complex workloads to analyze performance bottlenecks and optimization thresholds.

**6. [AI Medical Consultation Voice LLM](https://github.com/iinaa-eimrit/AI-Medical-Consultation-Co-pilot-Voice-LLM-)** | **[Live Demo](https://ai-medical-consultation-co-pilot-vo.vercel.app)**
A voice-to-voice AI co-pilot for medical consultations.
**Tech Stack:** TypeScript, WebSockets, LLMs, Audio Streaming.
**Engineering Feat:** Engineered a real-time asynchronous pipeline handling continuous audio streaming, live transcription, and text-to-speech with stringent low-latency constraints.

---

### Open Source Contributions

I actively contribute to distributed orchestration and agentic AI frameworks. I focus on architectural improvements, LLM reliability, and performance bottlenecks.
* **`aden-hive/hive`:** Engineered an LLM self-correction loop within the orchestrator, automatically feeding validation errors back to the model to improve tool-calling reliability. [View Pull Request](https://github.com/aden-hive/hive/pull/7382)
* **`rivet-dev/actors`:** Engineered external OIDC/JWT validation inside `onAuth` lifecycle hooks to support enterprise authentication. [View Pull Request](https://github.com/rivet-dev/actors/pull/5572)
* **`rivet-dev/actors`:** Identified and benchmarked a severe O(N) array lookup CPU bottleneck occurring under high load in the runner tunnel. [View Architecture Issue](https://github.com/rivet-dev/actors/issues/5581)
