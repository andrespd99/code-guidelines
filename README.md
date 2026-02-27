# Engineering Guidelines

> A living collection of opinionated, practical guidelines for building software that teams are proud to work on — and proud to show others.

These guidelines are not a list of rules to memorize. They are a shared vocabulary and a set of deliberate decisions, with the reasoning behind them, so every developer understands not just *what* to do but *why*. The goal is a codebase where every new feature feels natural to add, every pivot feels manageable, and any experienced developer can navigate an unfamiliar part of the codebase in minutes.

---

## Principles That Cross All Technologies

Regardless of language, stack, or team, these principles run through every guideline in this repository:

| Principle | What it means in practice |
|-----------|--------------------------|
| **Readable over clever** | Code is written once and read hundreds of times. Optimize for the reader. |
| **Explicit over implicit** | Name what you mean. No magic, no hidden side effects, no surprising behavior. |
| **Consistent over personal** | A codebase is a shared space. Conventions exist so the team moves as one. |
| **Fail fast, fail loudly** | Validate at the boundary. Surface problems immediately. Never silently swallow a failure. |
| **Pragmatic over dogmatic** | Every pattern has a cost. Apply guidelines with judgment, not religion. |
| **Don't abstract prematurely** | Wait for the third use case before extracting a pattern. The wrong abstraction is worse than duplication. |

---

## Available Guidelines

| Technology | Domain | Topics Covered |
|------------|--------|----------------|
| [Flutter / Dart](./docs/flutter/00-index.md) | Mobile & cross-platform apps | Clean Architecture · DDD · BLoC · Error Handling |
| [Go](./docs/go/README.md) | Backend APIs & services | Hexagonal Architecture · HTTP · Testing · Concurrency |

---

## Flutter / Dart

Architecture-first guidelines for building mobile and cross-platform applications. Grounded in **Clean Architecture** and **Domain-Driven Design**, with [flutter_bloc](https://pub.dev/packages/flutter_bloc) as the state management layer.

<details>
<summary><strong>View all Flutter topics</strong></summary>

**Cross-Cutting**
- [Architecture](./docs/flutter/01-architecture.md) — Four-layer architecture, DDD concepts, dependency rules
- [Folder Structure](./docs/flutter/02-folder-structure.md) — Project layout and file organization
- [Naming Conventions](./docs/flutter/03-naming-conventions.md) — Files, classes, variables, suffixes
- [Error Handling](./docs/flutter/04-error-handling.md) — `Either`, `TaskEither`, domain errors
- [State Management](./docs/flutter/05-state-management.md) — Bloc overview and usage rules

**Domain Layer**
- [Overview](./docs/flutter/domain/domain.md)
- [Entities](./docs/flutter/domain/entities.md)
- [Enums](./docs/flutter/domain/enums.md)
- [Repository Interfaces](./docs/flutter/domain/repositories.md)
- [Validators](./docs/flutter/domain/validators.md)

**Application Layer**
- [Overview](./docs/flutter/application/application.md)
- [Use Cases](./docs/flutter/application/use-cases.md)

**Infrastructure Layer**
- [Overview](./docs/flutter/infrastructure/infrastructure.md)
- [Data Sources](./docs/flutter/infrastructure/data-sources.md)
- [DTOs](./docs/flutter/infrastructure/dtos.md)
- [Repository Implementations](./docs/flutter/infrastructure/repositories.md)

**Presentation Layer**
- [Overview](./docs/flutter/presentation/presentation.md)
- [Feature Structure](./docs/flutter/presentation/features/features.md) · [Pages](./docs/flutter/presentation/features/pages.md) · [Views](./docs/flutter/presentation/features/view.md) · [Bodies](./docs/flutter/presentation/features/body.md)
- [Bloc Overview](./docs/flutter/presentation/blocs/blocs.md) · [Events](./docs/flutter/presentation/blocs/events.md) · [States](./docs/flutter/presentation/blocs/states.md)

</details>

→ **[Start reading the Flutter guidelines](./docs/flutter/00-index.md)**

---

## Go

Architecture-first guidelines for building backend APIs and services. Built around **Hexagonal Architecture** (Ports & Adapters), with [Chi](https://github.com/go-chi/chi) as the preferred HTTP router and [sqlc](https://sqlc.dev/) for type-safe database access.

<details>
<summary><strong>View all Go topics</strong></summary>

| # | Guide | What it covers |
|---|-------|----------------|
| 1 | [Project Layout](./docs/go/01-project-layout.md) | Monorepo structure, where things live and why |
| 2 | [Package Design](./docs/go/02-package-design.md) | Naming, cohesion, avoiding common traps |
| 3 | [Architecture](./docs/go/03-architecture.md) | Hexagonal architecture, ports & adapters, dependency direction |
| 4 | [Interface Design](./docs/go/04-interface-design.md) | Small interfaces, consumer-defined contracts |
| 5 | [Error Handling](./docs/go/05-error-handling.md) | Wrapping, sentinel errors, translation boundaries |
| 6 | [Dependency Injection](./docs/go/06-dependency-injection.md) | Constructor pattern, explicit wiring, no global state |
| 7 | [Concurrency](./docs/go/07-concurrency.md) | Goroutines, errgroup, avoiding leaks |
| 8 | [Testing](./docs/go/08-testing.md) | Table-driven tests, mocking strategy, integration tests |
| 9 | [Data Access](./docs/go/09-data-access.md) | Repository pattern, sqlc, transactions, migrations |
| 10 | [Configuration](./docs/go/10-configuration.md) | Env-based config, fail-fast validation |
| 11 | [Observability](./docs/go/11-observability.md) | Structured logging, Prometheus, tracing, health checks |
| 12 | [HTTP Layer](./docs/go/12-http-layer.md) | Chi, middleware, handler design, request/response DTOs |
| 13 | [Tooling](./docs/go/13-tooling.md) | Linting, Taskfile, code generation, CI pipeline |

</details>

→ **[Start reading the Go guidelines](./docs/go/README.md)**

---

## Repository Structure

```
docs/
├── flutter/            Flutter & Dart guidelines
│   ├── 00-index.md     ← start here
│   ├── domain/
│   ├── application/
│   ├── infrastructure/
│   └── presentation/
└── go/                 Go guidelines
    ├── README.md        ← start here
    ├── 01-project-layout.md
    └── ...
```

---

## Contributing

These guidelines are a living document. They should evolve as the team learns, as the ecosystem matures, and as we encounter new problems worth solving consistently.

**To improve an existing guideline:** Open a PR with the change and a brief explanation of why. Link to examples or prior art where helpful.

**To add a new technology:** Create a `docs/<technology>/` directory and open a PR. Include at minimum an index file that covers the architecture philosophy, project structure, and the most impactful patterns for that stack.

**To challenge a guideline:** Open an issue. Good arguments change guidelines. "I prefer it the other way" does not.
