# Aditya Shelke

### Software Engineer · Distributed Systems · Backend · Full Stack · Applied AI

I build software that has to keep working after the happy path ends.

My work sits across **distributed backend systems, product engineering, cloud infrastructure, and applied AI** — with a strong focus on reliability, observability, clean interfaces, and systems that are easy for other engineers to reason about.

Currently working on backend systems in the payments space, where correctness, idempotency, failure recovery, and operational visibility aren't nice-to-haves — they're part of the product.

---

## `> engineering philosophy`

```text
Correctness > cleverness
Observability > assumptions
Simple interfaces > hidden complexity
Measure before optimizing
Design for failure
Ship, learn, improve
```

I like systems where the interesting problems happen between components:

- duplicate events
- partial failures
- retries and timeouts
- concurrent state
- cache consistency
- schema evolution
- service boundaries
- backpressure
- degraded dependencies
- production debugging

That usually means thinking beyond:

> "Does the code work?"

and asking:

> "What happens when this runs across multiple services, machines, regions, retries, and failure modes?"

---

## `> current stack`

```yaml
languages:
  - Python
  - Java
  - TypeScript
  - JavaScript

backend:
  - FastAPI
  - Spring Boot
  - Node.js
  - REST
  - gRPC
  - WebSockets

frontend:
  - React
  - Angular

distributed_systems:
  - Kafka
  - Redis
  - Event Driven Architecture
  - Idempotent Processing
  - Async Workers

data:
  - PostgreSQL
  - SQL

infrastructure:
  - AWS
  - Docker
  - Kubernetes

observability:
  - OpenTelemetry
  - Grafana
  - Metrics
  - Tracing
  - SLOs

applied_ai:
  - LangGraph
  - LangChain
  - RAG
  - MCP
  - LLM Agents
```

---

# Selected Engineering Work

## 🧩 Conflux

**Offline-first collaborative workspace engineered around distributed state and eventual convergence.**

Not another CRUD collaboration app.

Conflux explores what happens when multiple users modify shared state while clients are offline, reconnect out of order, and communicate through multiple application nodes.

### Architecture

```text
            ┌──────────────┐
            │ React Client │
            └──────┬───────┘
                   │
          IndexedDB Mutation Queue
                   │
             WebSocket Layer
                   │
        ┌──────────▼──────────┐
        │   Fastify Nodes     │
        └──────────┬──────────┘
                   │
             Redis Pub/Sub
                   │
       ┌───────────▼───────────┐
       │ PostgreSQL Event Log  │
       └───────────────────────┘
```

**Engineering focus**

- Hand-implemented **RGA CRDT**
- Offline mutation queue with deterministic replay
- Property-based convergence testing
- Append-only event log
- Snapshot recovery
- Multi-node synchronization
- Conflict-free concurrent editing
- p99 synchronization benchmarking

`TypeScript` `React` `Fastify` `WebSockets` `PostgreSQL` `Redis` `Docker`

---

## 🤖 Patchwork

**Autonomous code-repair system that treats an LLM as one component inside a reliable execution engine.**

Given a repository and an issue, Patchwork can inspect the codebase, form a repair plan, modify files, execute tests, inspect failures, iterate, and produce a reviewable patch.

```text
Issue
  │
  ▼
Planner
  │
  ▼
Repository Explorer
  │
  ▼
Sandboxed Executor
  │
  ├── Modify Code
  ├── Run Tests
  ├── Observe Failure
  └── Retry
  │
  ▼
Patch + Explanation
```

The interesting part isn't the prompt.

It's everything around it.

**Engineering focus**

- Sandboxed execution
- Persistent agent state
- Idempotent step execution
- Retry + exponential backoff
- Cancellation and timeouts
- Dependency-aware execution
- Failure recovery
- Structured tool interfaces
- Execution telemetry
- Autonomous test-feedback loops

`Python` `Docker` `GitHub API` `LLMs` `Agentic Systems`

---

# Production Engineering

Some areas I spend a lot of time thinking about:

### Event processing

```text
event_received()
      ↓
validate()
      ↓
deduplicate()
      ↓
process()
      ↓
persist()
      ↓
acknowledge()
```

Because in distributed systems:

```text
"processed once"
```

and

```text
"delivered once"
```

are very different guarantees.

### Observability

Logs tell you **what happened**.

Metrics tell you **how often it happens**.

Traces tell you **where the time went**.

Good production systems need all three.

### API design

I care about APIs that are:

```text
Predictable
Versionable
Observable
Idempotent
Well-bounded
Hard to misuse
```

---

# Applied AI

I’m interested in AI systems when AI actually earns its place in the architecture.

My preference is:

```text
LLM
  +
Deterministic Software
  +
Retrieval
  +
Tooling
  +
State
  +
Guardrails
  +
Evaluation
  +
Observability
```

rather than:

```text
prompt → hope
```

The model can be probabilistic.

The surrounding system shouldn't be.

---

# What I Optimize For

| Area | What matters |
|---|---|
| Reliability | predictable behavior under failure |
| Architecture | clear boundaries and ownership |
| APIs | contracts that are difficult to misuse |
| Distributed Systems | idempotency, consistency, retries |
| Performance | measured bottlenecks, not guesses |
| Observability | debugging without archaeology |
| AI Systems | controlled autonomy |
| Code | boring where boring is better |

---

# Currently Exploring

```text
Distributed Systems
├── CRDTs
├── Event-driven architecture
├── Consensus & consistency
├── Failure recovery
└── Multi-node coordination

AI Engineering
├── Agent runtimes
├── Tool execution
├── Sandboxing
├── Agent state machines
└── Reliable LLM workflows

Backend Engineering
├── Service boundaries
├── High-throughput APIs
├── Async processing
├── Caching
└── Observability
```

---

# Beyond the Code

I earned my **M.S. in Computer Science from Syracuse University** and enjoy working on engineering problems where software architecture has real operational consequences.

I'm especially interested in teams building:

**distributed systems · developer infrastructure · payments · cloud platforms · AI-native products**

---

<div align="center">

### Build systems that are easy to operate, not just easy to demo.

[LinkedIn](https://www.linkedin.com/in/adityashelke7/) · Projects · Engineering Notes

</div>
