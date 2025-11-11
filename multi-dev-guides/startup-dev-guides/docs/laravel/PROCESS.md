# How we work — Laravel (PROCESS)

Purpose
-------
This document captures how teams typically run Laravel/PHP projects in industry: required artifacts, deployment patterns, testing, and release practices.

Roles & responsibilities
------------------------
- PM: product scope and acceptance criteria.
- TL/Lead: system architecture, critical tech decisions, code reviews.
- Developers: feature implementation, tests, and code quality.
- QA/DevOps: test plans, CI/CD, deployment and monitoring.

Project flow
------------
1. Requirements & PRD
2. Architecture & Data model (TSD)
3. Implementation with feature flags if needed
4. Testing (unit, integration, browser/acceptance)
5. Deploy (CI builds Docker images / releases)

Essential documents
-------------------
- PRD, TSD/SDD, API Spec, Test Plan, Deployment Checklist, Release Notes.

CI & testing
------------
- Use GitHub Actions / GitLab CI to run PHP linting (PHP_CodeSniffer), static analysis (Psalm or PHPStan), and tests (PHPUnit, Pest).
- Run browser tests (Dusk or Playwright) for end‑to‑end flows.

Deployment patterns
-------------------
- Containerized deployment is common (Docker + Kubernetes or managed services).
- For simpler setups, use Forge, Vapor (serverless), or traditional VPS deployment with orchestration scripts.
- Database migrations must be orchestrated with careful rollout strategies and backups.

Security & maintenance
----------------------
- Keep composer.lock committed and pin dependencies for reproducible builds.
- Regularly run dependency vulnerability scans (e.g., Dependabot) and apply security patches promptly.

Where to put docs
-----------------
- Project repository (docs/), plus canonical templates in `multi-dev-guides/startup-dev-guides/templates/`.

Next steps
----------
- Add sample CI workflows, dockerfile examples and a Laravel-specific release checklist in templates.
