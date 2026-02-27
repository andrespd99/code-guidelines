# Flutter Development Guidelines

This document is the entry point for the Flutter coding guidelines used across our projects. These rules exist to ensure **consistency**, **maintainability**, and **scalability** in every codebase.

## Philosophy

These guidelines are grounded in:

- **Domain-Driven Design (DDD)** — model software around real business concepts.
- **Clean Architecture** — separate concerns into layers with strict dependency rules.
- **Explicit over implicit** — code should be readable without needing to trace through layers of abstraction.

## Architecture at a Glance

We follow a **four-layer architecture**:

| Layer            | Responsibility                                              |
| ---------------- | ----------------------------------------------------------- |
| `domain`         | Core business rules, entities, errors, repository contracts |
| `application`    | Orchestration of domain logic (use cases)                   |
| `infrastructure` | External world: APIs, databases, local storage              |
| `presentation`   | UI, state management (Bloc), routing                        |

See [Architecture](./architecture.md) for the full explanation and dependency rules.

## Table of Contents

### Cross-Cutting Concerns
- [Architecture](./architecture.md) — Layer diagram, DDD concepts, dependency rules
- [Folder Structure](./folder-structure.md) — Project layout and file organization
- [Naming Conventions](./naming-conventions.md) — Files, classes, variables, suffixes
- [Error Handling](./error-handling.md) — `Either`, `TaskEither`, domain errors
- [State Management](./state-management.md) — Bloc overview and usage rules

### Domain Layer
- [Overview](./domain/domain.md)
- [Entities](./domain/entities.md)
- [Enums](./domain/enums.md)
- [Repository Interfaces](./domain/repositories.md)
- [Validators](./domain/validators.md)

### Application Layer
- [Overview](./application/application.md)
- [Use Cases](./application/use-cases.md)

### Infrastructure Layer
- [Overview](./infrastructure/infrastructure.md)
- [Data Sources](./infrastructure/data-sources.md)
- [DTOs](./infrastructure/dtos.md)
- [Repository Implementations](./infrastructure/repositories.md)

### Presentation Layer
- [Overview](./presentation/presentation.md)
- **Features**
  - [Feature Structure](./presentation/features/features.md)
  - [Pages](./presentation/features/pages.md)
  - [Views](./presentation/features/view.md)
  - [Bodies](./presentation/features/body.md)
- **Blocs**
  - [Bloc Overview](./presentation/blocs/blocs.md)
  - [Events](./presentation/blocs/events.md)
  - [States](./presentation/blocs/states.md)
