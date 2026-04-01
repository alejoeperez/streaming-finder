# ADR-001: Initial project structure

## Status
Accepted

## Context
The project needs an initial structure that supports backend development, frontend development, and technical documentation in a simple and organized way.

## Decision
We will use a single repository with the following top-level folders:
- /backend
- /frontend
- /docs

## Alternatives Considered
- Separate repositories for frontend and backend
- Keeping documentation outside the repository

## Consequences

### Positive
- Simpler setup for the initial phase
- Easier coordination between frontend, backend, and documentation
- All project artifacts stay in one place

### Negative
- The repository may grow over time
- Independent pipelines may require extra setup later
