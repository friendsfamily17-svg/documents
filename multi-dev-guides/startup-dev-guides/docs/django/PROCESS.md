Django — PROCESS

Project lifecycle (recommended flow):

1. Intake & PRD
   - Product provides a short PRD; engineering scopes migrations and data model changes.

2. Design & DB changes
   - Prepare migration strategy; consider backfilling and feature flags for schema changes.

3. Implementation
   - Include migrations and tests in the same PR; run `python manage.py test` in CI.

4. CI & Review
   - CI should run linters (flake8/ruff), tests, and security checks.

5. Staging & Release
   - Run migrations on staging, validate and then deploy with safe migration procedure (transactional or phased).

6. Post-release
   - Monitor metrics, error rates, and DB performance.

Attach PRD, TSD, migrations, and deployment checklist to significant PRs.
