# Go Coding Guidelines

> A practical, opinionated guide to writing idiomatic, scalable Go for backend APIs.

These guidelines are written for teams building backend services in a Go monorepo. They are **opinionated by design** — the goal is to reduce the number of decisions any developer has to make and create a codebase where every new feature feels natural to add, and every product pivot feels manageable.

---

## Core Principles

These principles run through every guideline. When in doubt, come back to them.

| Principle | What it means |
|-----------|---------------|
| **Boring is good** | Predictable code is maintainable code. A new team member should read any file and understand it without context. Clever code is a liability. |
| **Explicit over implicit** | Name what you mean. No magic initialization, no hidden dependencies, no surprise side effects. |
| **Fail fast, fail loudly** | Validate at boundaries. Return errors early. Crash at startup if configuration is invalid. Never silently swallow an error. |
| **Composition over hierarchy** | Small, focused interfaces compose better than deep type trees. |
| **Standard library first** | Go's stdlib is excellent. Add a dependency only when the value is clear and the maintenance cost is understood. |
| **Don't abstract prematurely** | Wait for the third use case before extracting a pattern. The wrong abstraction is worse than duplication. |

---

## Index

| # | Guide | What it covers |
|---|-------|----------------|
| 1 | [Project Layout](./01-project-layout.md) | Monorepo directory structure, where things live and why |
| 2 | [Package Design](./02-package-design.md) | Naming, cohesion, the `internal/` boundary |
| 3 | [Architecture](./03-architecture.md) | Hexagonal architecture, ports & adapters, dependency direction |
| 4 | [Interface Design](./04-interface-design.md) | Small interfaces, consumer-defined contracts, composition |
| 5 | [Error Handling](./05-error-handling.md) | Wrapping, sentinel errors, error translation boundaries |
| 6 | [Dependency Injection](./06-dependency-injection.md) | Constructor pattern, explicit wiring, no global state |
| 7 | [Concurrency](./07-concurrency.md) | Goroutines, errgroup, avoiding leaks, channels vs mutexes |
| 8 | [Testing](./08-testing.md) | Table-driven tests, mocking strategy, integration tests |
| 9 | [Data Access](./09-data-access.md) | Repository pattern, sqlc, transactions, migrations |
| 10 | [Configuration](./10-configuration.md) | Env-based config, fail-fast validation, config structs |
| 11 | [Observability](./11-observability.md) | Structured logging, Prometheus metrics, tracing, health checks |
| 12 | [HTTP Layer](./12-http-layer.md) | Chi router, middleware, handler design, request/response DTOs |
| 13 | [Tooling](./13-tooling.md) | Linting, Taskfile, code generation, developer workflow |

---

## How to Use These Guidelines

- **New to the codebase?** Read the guides in order — they build on each other.
- **Working on a specific problem?** Jump directly to the relevant guide.
- **Reviewing a PR?** Use the guides as a reference to anchor feedback in shared conventions.
- **Disagreeing with a guideline?** Open a discussion. Guidelines are living documents — they should evolve as the team learns.

---

[Start reading → Project Layout](./01-project-layout.md)
