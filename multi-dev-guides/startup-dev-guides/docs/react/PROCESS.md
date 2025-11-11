# How we work — React (PROCESS)

Purpose
-------
This document provides a practical workflow for frontend React projects: required documents, development lifecycle, CI/CD, release and monitoring recommendations.

Roles & responsibilities
------------------------
- PM: product decisions, acceptance criteria, and rollout plan.
- TL: frontend architecture, performance budget, and key tech decisions.
- Developers: implement features, follow component library and styling system.
- QA: test plans, visual regression, cross‑browser checks.
- DevOps: CI/CD pipelines, hosting, and monitoring.

Project stages
--------------
1. Intake & PRD: define user value, acceptance criteria, and success metrics.
2. Design & Accessibility: component design, visual specs, a11y requirements.
3. Implementation: component-driven development, Storybook for isolated components.
4. Testing: unit tests (Jest), integration and E2E (Cypress / Playwright), visual regression.
5. Release: bundle optimization, CDN and cache config, blue/green or canary releases.

Essential documents
-------------------
- PRD, TSD (app shell, caching strategy), Component spec, Test Plan, Deployment Checklist, Release Notes.

Developer experience & tooling
-----------------------------
- Use a component library and Storybook to document UI components.
- Linting and formatting (ESLint + Prettier) as precommit hooks.
- Fast feedback in CI with cached node_modules and parallelized steps.

CI & quality
------------
- Run linting, unit tests, and build in CI on each PR. Run E2E tests on merge or nightly runs.
- Monitor bundle size and performance budgets (Bundlephobia, webpack/bundler reports).

Deployment & hosting
--------------------
- Host static builds on CDN (Netlify, Vercel, CloudFront) or serve from an app host.
- Configure proper cache headers and invalidate caches on deploy if necessary.

Handoff checklist
------------------
- Story or PR linked to PRD with acceptance criteria.
- Accessibility checks and cross‑browser test coverage.
- Performance checks (Lighthouse scores) for critical flows.

Where to store documents
------------------------
- Keep component specs and Storybook in the project repo; keep canonical PRD/TSD templates in `multi-dev-guides/startup-dev-guides/templates/`.

Next steps
----------
- Add sample CI workflows (GitHub Actions), Storybook publishing steps, and a React deployment checklist into `templates/`.
