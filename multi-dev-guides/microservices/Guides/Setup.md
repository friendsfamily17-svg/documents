# Microservices — Setup

General guidance for running a multi-service environment locally.

1. Prerequisites: Docker & docker-compose (or Docker Compose v2), make, and any language runtimes used by the services.

2. Start local services with compose:

- `docker-compose -f docker-compose.dev.yml up --build`

3. Service discovery and local DNS: ensure services register with the local network and ports are forwarded.

4. Running tests: run service-specific tests in parallel or via a test orchestrator.

5. Observability: enable logs and tracing (Jaeger/Zipkin) in dev if available.

Notes:

- Prefer running each service in its own terminal for rapid iteration, or use `make` targets to run common flows.
- Use `./scripts/setup_local_env.sh` if the repo provides one to seed DBs and test data.
