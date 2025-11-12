# Python — Common Errors & Quick Fixes

Short description
-----------------
Frequent issues when working on Python services and quick steps to resolve them.

## 1. Virtual environment not activated

- Symptom: `ModuleNotFoundError` on local imports.
- Fix: `source .venv/bin/activate` (or the appropriate activation command).

## 2. Dependency version conflicts

- Symptom: incompatible package version errors.
- Fix: pin versions in `requirements.txt` or use `poetry.lock` and reinstall.

## 3. Database connection failures

- Symptom: cannot connect to DB in tests or local run.
- Fix: verify env vars, connection string, and that the DB is running.

## 4. Failing migrations

- Symptom: migration errors on deploy.
- Fix: run migrations locally, check for backward incompatible changes, and add a migration plan.
