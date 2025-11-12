Microservices — SCENARIOS

Hands-on scenarios and checklists for microservice projects:

1) Add a new stateless service
   - Define service responsibility and API contract.
   - Add Dockerfile, health checks, and a CI pipeline.
   - Deploy to staging and run integration tests.

2) Database-per-service migration
   - Plan migration strategy for a single service-owned DB and include rollback.

3) Implement asynchronous processing
   - Add a message broker (e.g., Kafka/RabbitMQ), define schemas, and add consumer/producer tests.

4) Service-to-service authentication
   - Implement mutual TLS or JWT-based service tokens and document the trust model.

Reference templates in `../../templates/` and local setup in `../../../microservices/Guides/Setup.md`.
