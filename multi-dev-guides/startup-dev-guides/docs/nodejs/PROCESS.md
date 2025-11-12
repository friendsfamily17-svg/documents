Node.js (Express) — PROCESS

Project lifecycle and team flow (tailor to your company):

1. Intake & Discovery
   - Product files a short PRD (use `../../templates/PRD_TEMPLATE.md`).
   - Engineering provides a technical summary (TSD) and spike tasks if needed.

2. Design & Spec
   - Agree on API contract, auth, data model, and migration plan.
   - Add API contract to the SDD/TSD and update the PRD acceptance criteria.

3. Implementation
   - Create a feature branch and PR against `develop` or `main` per repo policy.
   - Include unit tests, integration tests, and update API docs (OpenAPI/Swagger) if present.

4. CI & Review
   - CI runs lint, unit tests, and integration tests.
   - Peer review focuses on API contract, error handling, and database migrations.

5. Staging & Release
   - Deploy to staging and run smoke tests (include migration run in a safe step).
   - Use blue/green or canary deployment patterns if supported.

6. Post-release
   - Monitor logs, metrics, and error budgets; be ready for rollback if necessary.

Documents to attach to PRs: link to PRD/TSD, migration scripts, deployment checklist.
