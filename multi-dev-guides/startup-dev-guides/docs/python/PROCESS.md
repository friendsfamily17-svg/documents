# How we work — Python (PROCESS)

Purpose
-------
This document describes how backend and Python services are run in real companies: roles, stages, required documents, testing, deployment and operational practices.

Roles & responsibilities
------------------------
- Product Manager (PM): defines features, success criteria and business constraints.
- Tech Lead (TL): architecture, data model, API design, and performance tradeoffs.
- Backend Engineers: implement services, write tests, and maintain infra as code.
- QA / SRE: create test plans, run load and integration tests, define SLAs.
- DevOps: CI/CD, infrastructure, secret management, observability.

Project stages
--------------
1. Intake and Discovery: collect requirements, estimate, and identify dependencies.
2. API / Data Design: design REST/GraphQL APIs and DB schema; create contract docs.
3. Implementation: code with unit/integration tests, use feature flags for gradual rollout.
4. Testing: automated integration tests, contract tests, and load tests.
5. Deployment: blue/green or canary releases, database migrations strategy.
6. Monitoring & Support: logs, traces, metrics, and incident runbooks.

Essential documents
-------------------
- PRD: product goals and acceptance criteria.
- API Spec: OpenAPI / gRPC proto files with examples.
- TSD/SDD: architecture diagrams, data model, scaling considerations.
- Test Plan: integration, contract, and load tests.
- DB Migration Plan: when and how to run migrations and rollbacks.
- Deployment Checklist & Runbook: rollout steps, monitoring checks, rollback plan.

Testing & CI
------------
- Unit tests: run on each PR (pytest / unittest).
- Integration tests: run in CI stage against ephemeral or staging environments.
- Contract tests: ensure consumer and provider compatibility (Pact or contract tests).
- Performance tests: scheduled or pre‑release load tests.

Branching & Releases
---------------------
- Trunk‑based development or GitFlow depending on org size. Prefer short‑lived branches and feature flags on trunk.
- Releases: automate via CI pipeline to tag and publish artifacts (docker images) to registries.

Deployment patterns
-------------------
- Containerize services and use Kubernetes or managed services.
- Use CI to build images, push to registry, run migrations in a controlled job, then deploy.
- Use feature flags and gradual rollouts for risky changes.

Operational practices
---------------------
- Observability: instrument code with metrics and distributed tracing (OpenTelemetry, Prometheus, Grafana).
- Alerts: set SLOs and alert thresholds.
- Incident response: playbooks, runbooks, and postmortems.

Where to put these documents
----------------------------
- Keep API specs and migration plans in the project repo; keep PRD/TSD in `multi-dev-guides/startup-dev-guides/templates/` for reuse.

Tech-specific notes
-------------------
- Packaging: create reproducible builds with pinned dependencies (requirements.txt / poetry / pyproject.toml).
- Security: keep secrets in vault/CI secrets; scan images for vulnerabilities.

Next steps / templates
---------------------
- Provide sample Dockerfile, GitHub Actions CI workflow, OpenAPI template, and DB migration checklist in the `templates/` folder.
