# Hi, I'm Amrit Raj 👋

**Backend-Heavy Full-Stack Engineer | Real-Time Systems & Distributed Data**

I engineer scalable backend systems and data-intensive full-stack platforms. I specialize in TypeScript, low-latency data streaming (WebSockets), database optimization (PostgreSQL/pgvector), and deploying serverless architectures to the edge.

- Currently architecting real-time streaming platforms and serverless APIs (Cloudflare Workers, Prisma Accelerate, Monorepos).
- Profiling open-source frameworks to resolve CPU bottlenecks and integrating enterprise-grade authentication (OIDC/JWT) at the infrastructure layer.
- Connect with me on [LinkedIn](https://www.linkedin.com/in/amrit-raj-8a30b8247) or reach out at amritraj4work@gmail.com.

---

### Projects

**1. [Stock Trading Platform](https://github.com/iinaa-eimrit/Stock-Trading-Platform)**
A low-latency trading engine handling concurrent orders and live tick data.
* **Architecture:** Built with TypeScript and Node.js. Designed a multiplexed WebSocket streaming architecture to push real-time market data to the React client without overwhelming the main thread.
* **Why it matters:** Demonstrates strict concurrency management, preventing race conditions in financial state management.

**2. [Multi-Workspace Document Assistant (RAG)](https://github.com/iinaa-eimrit/Multi-Workspace-Document-Assistant-RAG-Tool-Calling-)**
An enterprise-grade retrieval-augmented generation (RAG) pipeline with autonomous tool calling.
* **Architecture:** Implemented complex data chunking, vector similarity search, and a robust prompt-chaining loop to prevent LLM hallucinations.
* **Why it matters:** Proves ability to move beyond basic API wrappers into robust AI system orchestration.

**3. [Pen Pulse](https://github.com/iinaa-eimrit/Pen-Pulse)**
A highly scalable, serverless blogging API.
* **Architecture:** Deployed to the edge using Cloudflare Workers with a strict monorepo setup for shared Zod validation schemas. Leveraged Prisma Accelerate for distributed database connection pooling.

**4. [Space Shooter Game Engine](https://github.com/iinaa-eimrit/Space-Shooter-Game-Engine)**
A custom high-performance 2D game engine built from scratch.
* **Architecture:** Designed to demonstrate system-level programming, strict memory management, and rendering loop optimization.

**5. [Graph Database Cloud Benchmarking](https://github.com/iinaa-eimrit/Graph-Database-Cloud-Benchmarking)**
A comprehensive data engineering benchmark suite.
* **Architecture:** Rigorously compares CognoDB against other managed graph database cloud platforms using standardized, heavy-load datasets and complex workloads.

**6. [AI Medical Consultation Voice LLM](https://github.com/iinaa-eimrit/AI-Medical-Consultation-Co-pilot-Voice-LLM-)**
A voice-to-voice AI co-pilot for medical consultations.
* **Architecture:** Engineered a real-time asynchronous pipeline handling audio streaming, live transcription, and text-to-speech with stringent low-latency constraints.

---

### Open Source Contributions

I actively contribute to distributed orchestration and agentic AI frameworks. I focus on architectural improvements, LLM reliability, and performance bottlenecks.
* **`aden-hive/hive`:** Engineered an LLM self-correction loop within the orchestrator, automatically feeding validation errors back to the model to improve tool-calling reliability. [View Pull Request](https://github.com/aden-hive/hive/pull/7382)
* **`rivet-dev/actors`:** Engineered external OIDC/JWT validation inside `onAuth` lifecycle hooks to support enterprise authentication. [View Pull Request](https://github.com/rivet-dev/actors/pull/5572)
* **`rivet-dev/actors`:** Identified and benchmarked a severe O(N) array lookup CPU bottleneck occurring under high load in the runner tunnel. [View Architecture Issue](https://github.com/rivet-dev/actors/issues/5581)
