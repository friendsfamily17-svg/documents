# SCENARIOS.md — Flutter

## Table of contents
- Purpose
- Scenario: Intake -> Post-Release
- Checklist
- Platform-specific notes
- Next steps

## Purpose
This file describes common project intake and delivery scenarios for Flutter projects and a concrete checklist the Flutter team should follow from project reception to delivery and post-release.

## Scenario: Company wins a new Flutter project

1. Intake & Triage
   - Receive project brief (from Sales/Product). Attach initial assets, success criteria, timeline.
   - Product Manager (PM) schedules a kickoff with stakeholders, and assigns an Owner and Tech Lead.
2. Discovery (1–2 weeks)
   - PM and Tech Lead run stakeholder interviews and capture user stories.
   - Tech Lead runs a quick feasibility spike (POC) for platform targets (iOS/Android/Web/Desktop as needed).
   - Produce initial PRD and TSD drafts and estimate effort.
3. Design & Prototyping
   - UX provides wireframes and interactive mocks; Flutter team builds a small prototype if needed.
   - Freeze core design tokens and theme variables to minimize later churn.
4. Planning & Sprinting
   - Break features into stories, size them, and add to backlog.
   - Create CI pipeline and test matrix (unit, widget, integration) for the repo.
5. Development
   - Implement features with small PRs; require 1–2 approvals for merge.
   - Ensure `flutter analyze` and tests run on every PR.
6. QA & Release
   - QA runs on emulators and select real devices; run integration tests in CI.
   - Prepare release builds for each platform; submit to app stores or host web builds.
7. Post-Release
   - Monitor via Crashlytics/Sentry and rollout metrics. Hotfix if necessary.
   - Conduct a post-mortem and update the SCENARIOS checklist.

## Flutter Team Checklist (quick)
- ✅ Project brief and PRD received and stored in docs
- ✅ Platform targets confirmed (iOS / Android / Web / Desktop)
- ✅ Spike/POC completed for risky areas (plugins, native integrations)
- ✅ CI configured: build, analyze, test matrix (unit/widget/integration)
- ✅ Linting and code style enforced (`dart format`, `dart analyze`)
- ✅ Release process documented (App Store, Play Store, web host)
- ✅ Accessibility and localization considerations noted
- ✅ Monitoring configured (Crashlytics/Sentry)

## Platform-specific notes
- iOS: require macOS build machines for archival; account for App Store review times.
- Android: prepare AAB, signing keys, and Play Console release tracks.
- Web: cache/asset optimization; configure CDN and HTTPS.

---

If you want a PR-ready GitHub Actions snippet or a sample `fastlane` config added to templates, request it and I'll add one under `templates/`.
# Project Scenarios — Flutter

This document describes common scenarios and the step-by-step actions a Flutter team should take when the company accepts a new mobile/web/desktop project.

## 1. Project Intake (Day 0–3)
- Receive high-level brief from Product/Client.
- Gather attachments: designs, API contracts, acceptance criteria, timelines, constraints.
- Assign initial stakeholders: PM, Tech Lead, Designer, QA lead.

## 2. Discovery & Planning (Week 1)
- Run a short discovery spike (1–3 days) to validate feasibility (platform targets, native integration, plugin availability).
- Produce a short PRD and a Technical Spec (TSD) covering target platforms (iOS/Android/Web/Desktop), architecture, and 3rd-party services.
- Create engineering tickets and a milestone schedule (MVP + iterative releases).

## 3. Environment & Onboarding (Week 1)
- Create repo skeleton or confirm existing repo.
- Set up Flutter SDK version and lock `dart`/`flutter` versions in README.
- Create CI skeleton (build + analyze + test) and register secrets for code signing in secret store.

## 4. Development Iterations (Weeks 2+)
- Implement core flows in small increments with feature branches.
- Use state management pattern chosen at design (Provider/Riverpod/BLoC).
- Add unit/widget tests; run them in CI.

## 5. QA & UAT
- Run integration and end-to-end tests on CI and on device farms (Firebase Test Lab).
- Perform internal UAT, then external UAT with stakeholders.

## 6. Release & Post-Release
- Prepare store assets and follow platform signing steps (iOS App Store, Google Play). For web/desktop follow relevant packaging steps.
- Monitor releases with Crashlytics/Sentry and roll out hotfixes if needed.

## Tech-specific checklist
- Device matrix: list supported OS versions and device families.
- Signing: confirm keystore/certificates and rotation plan.
- Build flavors: define dev/staging/prod flavors and config mechanism.

---
If you'd like a templated checklist or a GitHub Actions example for Flutter builds, I can add that to `templates/`.
