# SCENARIOS.md — Python

## Purpose
Scenario guidance for Python projects: intake, discovery, delivery and operational checklist.

## Scenario: Company receives a backend or data project in Python

1. Intake & Triage
   - Collect requirements, datasets, SLAs, and environment constraints.
   - Assign PM, Tech Lead, and DevOps contact.
2. Discovery & Spike
   - Run architecture spike: choose framework (Flask/Django/FastAPI), DB, and hosting model.
   - Identify long-running tasks, background jobs, and scaling needs.
3. Design & Spec
   - Create TSD and API contract (OpenAPI/Swagger) and data model drafts.
4. Setup & CI
   - Create repo skeleton with virtualenv/poetry, linting, and pre-commit hooks.
   - Define CI: tests, static analysis (flake8/pylint), and security checks (pip-audit).
5. Development
   - Implement features with feature branches, small PRs, and code review.
   - Add unit tests and integration tests; mock external services.
6. Staging & Deployment
   - Use containerization (Docker) for parity; deploy to staging and run smoke tests.
   - Run migrations, seeders, and validation before production rollout.
7. Post-Launch
   - Monitor CPU, memory, latencies, and error rates; configure alerts (Prometheus/Sentry).

## Python Team Checklist (quick)
- ✅ Requirements and success metrics recorded
- ✅ Framework and runtime selected (Django/Flask/FastAPI)
- ✅ Virtual environment and dependency management (poetry/requirements.txt)
- ✅ Tests and coverage reported in CI
- ✅ Dockerfile and deployment steps documented
- ✅ Database migrations strategy and backups defined
- ✅ Monitoring and logging enabled (Sentry/Prometheus)

## Operational notes
- Use connection pooling for DB-heavy workloads.
- For batch/data projects, document data retention, ETL cadence, and idempotency.
# Project Scenarios — Python

This document outlines common scenarios and the step-by-step actions for a Python team when the company accepts a new project (web service, API, or data pipeline).

## 1. Intake & Triage (Day 0–3)
- Collect requirements, SLA expectations, expected traffic, and compliance needs.
- Identify primary runtime environment (WSGI/ASGI, serverless, containerized).
- Assign PM, Tech Lead, and DevOps contact.

## 2. Discovery & Architecture (Week 1)
- Run a technical spike to validate dependencies and third-party services.
- Produce TSD covering frameworks (Django/Flask/FastAPI), DB choices, caching, and scaling strategy.

## 3. Environment & Repo Setup
- Create repo with a recommended layout and `pyproject.toml` / `requirements.txt`.
- Add `venv`/Poetry/Poetry lock file and CI config that runs linting, tests, and type checks.

## 4. Development
- Follow microtasks with clear unit tests and CI gating.
- Use feature toggles for large changes and staging environments for integration testing.

## 5. Pre-Release & Release
- Prepare container images (Dockerfile) and automated deployments (CI/CD pipelines).  
- Run load tests if traffic is expected to be significant.

## 6. Post-Release
- Monitor with Prometheus/Sentry/ELK.  
- Run post-mortem for incidents and update runbooks.

## Tech-specific checklist
- Decide runtime: Gunicorn + Uvicorn (ASGI) vs Gunicorn (WSGI).  
- Database migrations: migration strategy and backward compatibility.  
- Secrets & configuration: use vault or environment variables; avoid committing secrets.

---
I can also add a sample Dockerfile and GitHub Actions pipeline to `templates/` if you want.
