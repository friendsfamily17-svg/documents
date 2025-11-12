Microservices — Common Errors & Fixes

Common distributed-systems issues and quick remediation:

- Port collisions: ensure unique ports per service or use dynamic port assignment.
- Networking issues between containers: check docker network, service names, and environment DNS.
- Partial failures / retries: implement idempotency and safe retry policies for external calls.
- Deadlocks and DB contention: review transactions and use optimistic locking when appropriate.
- Observability gaps: add structured logs, metrics, and request IDs for tracing across services.
- Schema drift between services: version APIs and document contracts carefully (OpenAPI).

If you find recurring service-specific issues, add them here and link to the responsible service docs.
