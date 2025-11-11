# How we work — Flutter (PROCESS)

Purpose
-------
This document explains how real companies run Flutter projects end-to-end: roles, stages, necessary documents, handoffs, and operational practices. Use this as the canonical team workflow and checklist for Flutter projects.

Roles & responsibilities
------------------------
- Product Manager (PM): owns the product vision, PRD, stakeholder alignment, priorities and acceptance criteria.
- Tech Lead (TL): owns technical approach, architecture, feasibility, estimates, and technical reviews.
- Developers: implement features, write tests, follow code review process.
- QA / Testers: create and run test plans, verify acceptance criteria, run manual and automated tests.
- DevOps / SRE: CI/CD pipelines, infrastructure, releases, monitoring and rollback procedures.

Project stages (what happens in a real company)
---------------------------------------------
1. Intake / Kickoff
   - PM collects requirements and writes a short brief. Attach timelines, target platforms, stakeholders.
   - Assign TL and Owner. Schedule a kickoff meeting.
   - Documents: initial brief, stakeholder list, project timeline.

2. Discovery & Feasibility (1–2 weeks)
   - TL and senior devs run spikes / POCs for risky areas (native plugins, performance, authentication flows).
   - Validate third‑party SDKs and licensing.
   - Documents: Feasibility notes, rough technical approach, updated estimates.

3. Product & Technical Spec
   - PM authors PRD (user problems, acceptance criteria, success metrics). PRD is the source of truth for scope.
   - TL authors TSD (architecture, data flows, high‑level diagrams) and API contracts if applicable.
   - Documents: PRD, TSD, API Spec (OpenAPI or contract), UX wireframes and design tokens.

4. Design Handoff
   - UX hands off mocks, component specs and accessibility requirements.
   - Freeze tokens, typography, color, spacing to prevent churn.
   - Documents: design files, component specs, asset catalog.

5. Planning & Sprinting
   - Break PRD into epics and stories with clear acceptance criteria and test cases.
   - Estimate and schedule work (two‑week sprints are common).
   - Documents: Sprint backlog, user stories, acceptance tests.

6. Implementation
   - Small, focused PRs. Enforce linting, formatting (dart format), and static analysis (`dart analyze`).
   - CI runs tests (unit, widget, integration) on every PR. Require code review and passing CI before merge.
   - Documents: code, PRs, inline code reviews, CI logs.

7. QA & Pre-release
   - QA runs integration tests on real devices/emulators and smoke tests in staging.
   - Prepare release artifacts (iOS archive, Android AAB, web build) and run store prechecks.
   - Documents: Test Plan, Release Notes draft, Deployment Checklist.

8. Release & Post-release
   - Deploy to production (app stores or web host). Monitor crash reports and metrics (Crashlytics, Sentry, analytics).
   - Execute rollback plan if critical issues occur.
   - Conduct post‑release retrospective and update documentation.
   - Documents: Release Notes, Postmortem (if needed).

Essential documents (what to maintain)
-------------------------------------
- PRD (Product Requirements Document): user problems, success metrics, acceptance criteria, constraints.
- TSD (Technical Specification Document): architecture diagrams, API contracts, integration points.
- SDD (Solution Design Document) / Implementation notes: detailed design for complex features.
- API Spec (OpenAPI / contract): for backend integrations.
- Test Plan: test cases, environments, devices, pass/fail criteria.
- Deployment Checklist: platform‑specific steps, store accounts, signing keys, environment variables.
- Release Notes & Changelog: user‑facing changes and known issues.
- Monitoring & Runbook: where to check metrics, how to respond to incidents.

Branching, CI & quality gates
-----------------------------
- Branching: adopt trunk‑based or GitFlow depending on org size. For startups, trunk‑based with feature branches + short‑lived PRs is common.
- Pull Requests: require at least one reviewer and passing CI (lint + unit + widget tests). Use draft PRs for WIP.
- CI: run `dart analyze`, unit tests, widget tests. Run slower integration tests on scheduled/nightly runners or an integration stage.
- Quality gates: enforce code coverage thresholds and static analysis as needed.

Handoff checklist (before merge to main/release branch)
------------------------------------------------------
- PR linked to a user story and PRD acceptance criteria.
- Automated tests added or updated.
- Design assets included or referenced.
- Release checklist updated for platform-specific steps.
- Monitoring dashboard and alerts updated for new metrics.

Tech-specific notes
-------------------
- iOS: ensure macOS CI runners or use cloud builders (Codemagic) for archival; manage provisioning profiles and App Store credentials securely.
- Android: sign builds securely (keystore in CI secrets) and use AAB; configure Play Console tracks (internal, alpha, beta, production).
- Web: configure caching headers and CDN; optimize bundle size and critical assets.

Where to put these documents
----------------------------
- Store PRD/TSD/SDD and templates in `multi-dev-guides/startup-dev-guides/templates/` and project repo under `/docs` or a dedicated `docs/` folder.

Next steps / templates to add
----------------------------
- Add a sample PRD template per project, a release checklist snippet for Flutter, and example GitHub Actions workflows for flutter build/test. These can be placed in the `templates/` folder.
