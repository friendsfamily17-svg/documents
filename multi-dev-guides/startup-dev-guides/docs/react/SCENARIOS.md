# SCENARIOS.md — React

## Purpose
Describe project intake and team actions for React frontend projects, plus a concise checklist the React team can follow.

## Scenario: Frontend project awarded (React)

1. Intake & Kickoff
   - Capture acceptance criteria, performance targets, SSR/CSR needs, and hosting constraints.
   - Assign PM, Design Lead, and Frontend Tech Lead.
2. Discovery & Spike
   - Decide on framework approach (CRA, Next.js, Gatsby), routing strategy, and global state approach.
   - Prototype critical flows (auth, heavy list rendering) to validate choices.
3. Design handoff & accessibility
   - Lock core design tokens, components, and accessibility requirements.
4. Repo & CI setup
   - Initialize repo with ESLint, Prettier, TypeScript (if used), and GitHub Actions for lint/test/build.
5. Development
   - Build components in isolation (Storybook recommended), use small PRs, and require review.
   - Add unit and integration tests (Jest, React Testing Library). End-to-end tests (Cypress) for critical flows.
6. Performance & Release
   - Run Lighthouse audits, code-splitting, and optimize images/assets.
   - Deploy to hosting (Vercel, Netlify, S3+CloudFront) and verify environment variable configuration.

## React Team Checklist (quick)
- ✅ Acceptance criteria and target devices recorded
- ✅ Framework decided (CRA/Next.js/Gatsby) and rationale documented
- ✅ Storybook for components or equivalent documented
- ✅ CI: lint, test, build pipeline in place
- ✅ Accessibility checks included (axe, manual runs)
- ✅ Performance budget and monitoring (Lighthouse, Sentry/LogRocket)

## Hosting notes
- SSR: ensure node server or platform that supports server-side rendering (Vercel/Next).
- Static: configure CDN and cache headers for immutable assets.
# Project Scenarios — React

This document describes the typical sequence of actions for a React frontend team when the company accepts a new project.

## 1. Intake & Requirements (Day 0–3)
- Collect designs (Figma), data contracts (API specs), and accessibility/performance targets.
- Identify SSR/CSR/SSG needs (Next.js/Gatsby/plain CRA).

## 2. Discovery & Architecture (Week 1)
- Spike to validate routing, state management, and any 3rd-party UI libraries.
- Produce a TSD including build targets, CDN strategy, and caching headers.

## 3. Repo & Environment
- Initialize repo with chosen framework and a standard folder layout.
- Add CI that runs lint, typecheck (if TS), unit and e2e tests.

## 4. Development
- Implement components with accessibility and performance in mind.  
- Use incremental rollouts and feature flags for risky user-facing features.

## 5. Release
- Build optimized production bundle and deploy to CDN/hosting (Vercel/Netlify/S3+CloudFront).
- Run real-user monitoring and synthetic tests post-release.

## 6. Post-Release
- Monitor errors and performance with Sentry/Datadog/Lighthouse CI.

## Tech-specific checklist
- Node and package manager version pinning (node/npm/yarn/pnpm).  
- Bundle size budgets and code-splitting strategy.  
- Accessibility checklist and automated a11y checks in CI.

---
I can also add example `package.json` scripts and a starter GitHub Actions workflow to `templates/` on request.
