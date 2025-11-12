Microservices — PROCESS

Recommended process when developing and operating microservices:

1. Service definition & contract
   - Draft a small PRD or service purpose statement.
   - Define API contract (OpenAPI) and events (if using event-driven architecture).

2. Lightweight design & data ownership
   - Keep services focused; define data ownership and database boundaries.

3. Development & CI
   - Keep a separate CI pipeline per service; run unit tests and contract tests.

4. Integration & staging
   - Use a staging environment that can run multiple services together (compose or k8s namespace).

5. Release & deployment
   - Prefer immutable deployments via containers; use canary or rolling updates.

6. Operate & observe
   - Add health checks, metrics, and distributed tracing.

Attach PRD/TSD, OpenAPI spec, and deployment checklist to service-level PRs.
