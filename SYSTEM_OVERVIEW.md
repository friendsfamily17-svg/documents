# System Overview — How the pieces fit together

Short description
-----------------
High-level overview showing how Flutter (frontend), React (frontend/web), Laravel (backend), and Python (API/services) roles typically interact in a small startup.

## The typical responsibilities

- Product / PM: defines features and acceptance criteria (PRD).
- Design: UX and component specs used by front-end teams.
- Frontend (Flutter / React): implement UI and integrate with APIs; own client-side validation and UX flows.
- Backend (Laravel / Python): implement APIs, business logic, data storage and background processing.
- QA / SRE: validate releases, manage CI/CD and monitoring.

## How they interact (simple flow)

1. PM writes a PRD describing a user need.
2. Design produces mocks and component specs.
3. Backend (Laravel/Python) defines API contracts (OpenAPI) and creates endpoints.
4. Frontend (Flutter for mobile, React for web) implements UI and calls backend APIs.
5. CI runs automated tests; staging deployment is used for QA.
6. Release: deploy backend first, then frontend; monitor metrics and roll back if needed.

## Why this matters

- Clear interfaces (API contracts) reduce integration bugs.
- Responsibilities and handoffs avoid duplicate work and speed up releases.

## Where to start

- If you're a frontend dev, open `startup-dev-guides/docs/<your-tech>/ONBOARDING.md`.
- If you're a backend dev, check the API contract and DB migration policies in the TSD/SDD templates.
