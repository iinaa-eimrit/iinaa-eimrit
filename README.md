# Hi, I'm Amrit Raj 👋

### Backend Software Engineer
*Python · TypeScript · PostgreSQL · APIs · Reliability · Performance*

I build data-intensive backend services where correctness, access control, and recovery matter. My work spans healthcare data pipelines and APIs, real-time systems, multi-tenant AI applications, and focused open-source contributions.

- **Target roles**: Backend Software Engineer, Software Engineer (Backend)
- **Core stack**: Python · TypeScript/Node.js · PostgreSQL · Django · Express · Docker
- **Location**: India · Open to remote opportunities
- **Contact**: [LinkedIn](https://www.linkedin.com/in/amrit-raj-8a30b8247) · [amritraj4work@gmail.com](mailto:amritraj4work@gmail.com)

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
