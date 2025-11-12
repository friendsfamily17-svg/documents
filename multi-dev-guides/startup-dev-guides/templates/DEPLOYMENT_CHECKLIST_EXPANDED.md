# Deployment Checklist — Expanded

🧱 What This Is
---------------
A detailed, repeatable checklist for preparing, executing and validating releases to production. Includes pre-deploy, deploy, and post-deploy steps with owners and expected durations.

📋 Why It’s Important
---------------------
- Reduces release risk by making steps explicit and repeatable.
- Documents rollbacks and emergency contacts for faster incident response.

🧩 Project Understanding
-----------------------
- Target environment(s) and constraints (cloud provider, region requirements).
- Data migration sensitivity (schema changes, large tables).

⚙️ Real-World Example
---------------------
For a Laravel app: include steps to warm caches, run zero-downtime DB migrations (php artisan migrate --force with a migration lock), deploy workers, and rotate config caches.

📌 Pre-Deployment (owner, checklist)
----------------------------------
- Code: PRs merged to release branch and code review completed (owner: Tech Lead)
- CI: All green (unit, integration, smoke) and test artifacts published (owner: CI)
- Release notes: Drafted and approved (owner: PM)
- Secrets: Verified in vault and accessible by deploy job (owner: DevOps)
- Backups: Snapshot DB and file stores (owner: DBA/DevOps)

🚀 Deployment Steps
-------------------
- Put system into maintenance mode if needed (owner: Release Engineer)
- Run database migrations (ordered steps) and verify migration health
- Deploy services in order (API → background workers → frontend) and verify each
- Run smoke tests and health checks (automated) — target time: 10–15 minutes

🩺 Post-Deploy Validation
-------------------------
- Run smoke and regression checks against production
- Monitor metrics and errors for the first 30–60 minutes
- Sanity check key business flows and conversion metrics (owner: PM)

🔁 Rollback Plan
----------------
- How to rollback container images or switch traffic (owner: DevOps)
- Database rollback guidance (when safe vs. when not safe)

📞 Communication Plan
---------------------
- Slack/Teams channel to notify, on-call escalation list, and stakeholder updates cadence.

✅ Best Practices / Tips
------------------------
- Automate as much as possible and keep the checklist as code (scripts run by CI).
- Practice your rollback procedure on staging so the team is familiar with timing and steps.
