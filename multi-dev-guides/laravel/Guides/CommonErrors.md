# Laravel — Common Errors & Quick Fixes

Short description
-----------------
Common Laravel issues and how to quickly fix them.

## 1. .env configuration missing

- Symptom: app key or DB connection problems.
- Fix: copy `.env.example` and run `php artisan key:generate`.

## 2. Composer dependency issues

- Symptom: class not found or incompatible versions.
- Fix: run `composer install` and verify `composer.lock`.

## 3. Queue workers failing

- Symptom: jobs stuck or crashing.
- Fix: check queue driver, restart workers, inspect logs.
