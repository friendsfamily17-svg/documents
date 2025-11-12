Node.js (Express) — SCENARIOS

Example scenarios and minimal checklists — useful as hands-on learning tasks for interns.

1) Add new API endpoint (CRUD) for Orders
   - Update PRD acceptance criteria.
   - Design API contract and document it (OpenAPI spec or README).
   - Add DB migration for the orders table and test fixtures.
   - Implement route, controller, service, and unit tests.
   - Add integration test covering create -> read -> delete.
   - Run migrations on staging and deploy.

2) Database migration and backfill
   - Write migration script; include rollback.
   - Test migration locally and on a disposable DB.
   - Prepare deployment checklist to run migration safely (maintenance window or transactional migration).

3) Add background worker for processing
   - Define job queue, visibility timeout and retry policy.
   - Add health checks and monitoring metrics.

Each scenario should reference templates in `../../templates/` and link to the project `Guides/Setup.md` for local testing.
