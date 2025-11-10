# SCENARIOS.md — Laravel

## Purpose
This file captures common scenarios and the team's checklist when a Laravel project is taken on by the company.

## Scenario: New Laravel project accepted

1. Intake
   - Gather business requirements, hosting expectations, and 3rd-party integrations.
   - Assign PM and Tech Lead; confirm database and external service SLAs.
2. Architecture spike
   - Confirm PHP version, queue drivers, cache store (Redis), and session store.
   - Prototype any custom packages or integrations.
3. Repo & environment setup
   - Create project skeleton with `composer.json`, `.env.example`, and Dockerfile.
   - Define migrations and seeders structure.
4. CI & tests
   - Configure GitHub Actions / CI to run `composer install`, `phpunit`, and static analysis (PHPStan/PHPCS).
5. Development & QA
   - Use feature branches and run tests in CI; require code review.
   - QA runs feature tests and Laravel Dusk for browser flows where applicable.
6. Release & Ops
   - Prepare release build (docker image or deployment artifact), run migrations with `--force`, and warm caches.
   - Ensure zero-downtime deployment process (Envoyer, rolling updates).

## Laravel Team Checklist (quick)
- ✅ `.env.example` and environment variables defined
- ✅ Composer dependencies audit completed
- ✅ Database migration and seed strategy documented
- ✅ Queue and scheduler setup documented (supervisor/cron)
- ✅ CI runs tests and static analysis on PRs
- ✅ Backup and rollback plan exists

## Ops notes
- Ensure appropriate file permissions and `storage` ownership.
- Use config caching (`php artisan config:cache`) and route caching for production.
# Project Scenarios — Laravel

This file describes typical steps a Laravel team should follow when the company takes on a new web project built with Laravel.

## 1. Intake & Compliance (Day 0–3)
- Gather requirements, expected traffic, and any compliance/security constraints.
- Identify payment, email, and third‑party integration needs.

## 2. Discovery & Plan (Week 1)
- Do a feasibility spike: packages, queue/backoff strategy, and caching layers.
- Produce a TSD including database schema, queue/backends, and scaling plan.

## 3. Repo & Environment
- Initialize repo with standard Laravel structure or confirm starter repo.
- Configure `composer.json`, PHP version, and CI pipelines (linting, tests, static analysis).

## 4. Development
- Implement features with migrations, seeders, and feature tests.
- Use environment-specific config and service providers for infra differences.

## 5. Release
- Build Docker images or deployment artifacts; run migrations in CI with `--force` on production as part of controlled deployment.
- Use zero-downtime deployment techniques where applicable.

## 6. Post-Release
- Monitor errors with Sentry and app metrics with New Relic or Prometheus.

## Tech-specific checklist
- PHP and Composer version pinning.
- Queue worker setup and process manager (supervisord/systemd).
- Backup and migration rollback plan.

---
Tell me if you want a sample `composer.json` snippet or a Laravel GitHub Actions workflow added to `templates/`.
